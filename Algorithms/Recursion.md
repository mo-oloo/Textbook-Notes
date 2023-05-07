# 1.1 Reductions
- Reduce one problem $X$ to another problem $Y$
- Solving for $Y$ is a black box for $X$, meaning $X$ is independent of $Y$.
- We can assume that the black box solves $Y$ correctly.

# 1.2 Simplify and Delegate
- Recursion is a type of reduction.
- If the problem can be solved directly, then solve it directly.
- If not, then reduce the problem to a simpler version of the same problem.
- In other words, it is either simple enough to be solved in one step, or it is complex and you need to simplify the problem and "give it to someone else".
	- The book calls "someone else" the *Recursion Fairy*.
	- AKA the *Induction Hypothesis*.
- Because we are simplifying/reducing the problem with recursion, we need a **base case** that can be solved without any further reduction.
	- We cannot have an infinite sequence.

# 1.3 Tower of Hanoi
- Tower of Hanoi Problem: How can we move a tower of $n$ disks from one peg to another, using a third spare peg as an occasional placeholder, without ever placing a disk on top of a smaller disk?![[Pasted image 20230506182122.png]]
- Strategy:
	- We want to move the entire tower from one peg to another.
		- We can't move the bottom disk because the smaller disks are on top.
	- We need to move $n-1$ disks off from the $n$-th disk to a placeholder disk.
	- Then, we move the $n$-th disk to its destination.
	- Finally, we move the $n-1$ disks from the placeholder to the destination.
- Our strategy allowed us to reduce the problem from $n$ disks to $n-1$ disks.
	- We solved it for $n$, but we don't know how to solve it for $n-1$. This is okay because how $n-1$ gets solved is a black box for us.
	- We can hand it off the problem to the *Recursion Fairy* and we don't have to worry about it anymore.
- When $n=0$, the problem is *trivial* (omg leiss reference) and we don't have to reduce the problem anymore.
- We **shouldn't** unearth the recursive sequence and try to see how it all works out. Our **only** task is to reduce the problem to a simpler version of it, or to solve it directly if it is possible.
- In terms of Induction, our base case is $n=0$, and for any $n\geq 1$, the Inductive Hypothesis implies that our algorithm correctly moves the top $n-1$ disks.

- Psuedocode for the Recursive Hanoi Algorithm:
```
Hanoi(n, src, dst, tmp):
if n>0
	Hanoi(n-1, src, tmp, dst)
	move disk n from src to dst
	Hanoi(n-1, tmp, dst, src)
```
- If $n>0$, then first we move $n-1$ disks from the starting(src) peg to the placeholder(tmp) peg, using the destination(dst) peg as a temporary peg. Then, we move the $n$-th disk from our starting peg to our destination peg with a single, simple move. Finally, we move back all the $n-1$ disks from the temporary peg to the destination peg by calling `Hanoi()` recursively.
- Let $T(n)$ denote the amount of moves it takes to transfer $n$ disks. This is equivalent to the running time of our algorithm.
	- Our vacuous base case implies that $T(0)=0$, and the more general recursive algorithm implies that $T(n)=2T(n-1)+1$ for any $n\geq 1.$ 
	- We can easily guess that the general equation for $T$ is $T(n)=2^n-1$ by writing out the first few values of $n$.
		- Prove this is true with a simple induction proof.
	- If we had $n=64$ disk, moving a tower of 64 disks would take $2^{64}-1=18,446,744,073,709,551,615$ moves. At a single move per second, it would take around 585 billion years to complete the algorithm.

# 1.4 Mergesort
1. Divide the input array into two parts that are roughly equal in size.
2. Recursively mergesort each part.
3. merge each sorted part into a single array.
![[Pasted image 20230506213634.png]]
- We delegate the second step to the Recursion Fairy.
- The merge step is a different independent subroutine.
- The mergesort algorithm is recursive.
- Pseudocode:
```
MergeSort(A[1..n]):
if n>1
	m <- floor(n/2)
	MergeSort(A[1..m])
	MergeSort(A[m+1..n])
	Merge(A[1..n], m)
```
```
Merge(A[1..n], m):
	i <- 1; j <- m+1
	for k <- 1 to n
		if j>n
			B[k] <- A[i]; i <- i+1
		else if i>m
			B[k] <- A[j]; j <- j+1
		else if A[i] < A[j]
			B[k] <- A[i]; i <- i+1
		else
			B[k] <- A[j]; j <- j+1
	for k <- 1 to n
		A[k] <- B[k]
```

Proof of Mergesort:
- **Lemma 1.1.** *Merge* correctly merges the subarrays $A[1..m]$ and $A[m+1..n],$ assuming those subarrays are sorted in the input.
- **Proof:** Let $A[1..n]$ be any array and $m$ any integer such that the subarrays $A[1..m]$ and $A[m+1..n]$ are sorted. We prove that for all $k$ from $0$ to $n,$ the last $n-k-1$ iterations of the main loop correctly merge $A[i..m]$ and $A[j..n]$ into $B[k..n]$. The proof procceds by induction on $n-k+1,$ the number of elements remaining to be merged.
  
  If $k>n,$ the algorithm correctly merges the two empty subarrays by doing absolutely nothing. This is the base case. Otherwise, there are four cases to consider for the $k$-th iteration of the main loop.
  - If $j>n$, then subarray $A[j..n]$ is empty, so $\min(A[i..m]\cup A[j..n])=A[i]$.
  - If $i>m$, then subarray $A[i..m]$ is empty, so $\min(A[i..m]\cup A[j..n])=A[j]$.
  - Otherwise, if $A[i]<A[j]$, then $\min(A[i..m]\cup A[j..n])=A[i].$
  - Otherwise, we **must** have $A[i]\geq A[j]$, and $\min(A[i..m]\cup A[j..n])=A[j].$ 
  In all four cases, $B[k]$ is correctly assigned the smallest element of $A[i..m]\cup A[j..n]$. In two cases with the assignment $B[k]\leftarrow A[i]$, the induction hypothesis implies that the last $n-k$ iterations of the main loop correctly merge $A[i+1..m]$ and $A[j..n]$ into $B[k+1..n]$. Similarly, in the other two cases the rest of the subarrays are correctly merged. $\square$

- **Theorem 1.2.** *MergeSort* correctly sorts any input array $A[i..n]$.
- **Proof:** We prove the theorem by induction on $n$. If $n\leq 1,$ the algorithm correctly does nothing. Otherwise, the induction hypothesis implies that our algorithm correctly sorts the two smaller subarrays $A[1..m]$ and $A[m+1..n]$, after which they are corrected merged into a single sorted array, by Lemma 1.1. $\square$

- We obtain the following recurrence relation for `MergeSort()`: $$T(n)=T(\lceil{n/2}\rceil)+T(\lfloor{n/2}\rfloor)+O(n).$$Using a technique called *domain transformations*, we can simplify the recurrence to $T(n)=2T(n/2)+O(n).$ The "all levels equals" case of the recursion tree method immediately implies the solution $T(n)=O(n\log{n})$.
	- We can verify the solution $T(n)=O(n\log{n})$ by induction.
	- We are going to go over *domain transformations* and recursion trees later in this chapter.

# 1.5 Quicksort
- We split the array **before** recursion, which is more difficult. However, merging the sorted arrays is trivial.
1. Choose a pivot element from the array.
2. Partition the array into three subarrays containing the elements smaller than the pivot, the pivot element itself, and the elements larger than the pivot.
3. Recursively quicksort the first and last subarrays (The array with smaller elements and the array with bigger elements).
![[Pasted image 20230506220456.png]]
