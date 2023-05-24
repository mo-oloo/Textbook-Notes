- Backtracking is a recursive strategy that constructs a solution to a computational problem incrementally, at one small piece at a time.
- When the algorithm needs to decide between multiple options to the next component of the solution, it evalues **every** alternative recursively and chooses the best one.
# 2.1 N-Queens
- The problem is to place $n$ queens on an $n\times n$ chessboard in a way that no two queens are attacking each other.
	- No two queens are in the same row, column, or diagonal.
![[Pasted image 20230523115812.png]]
- Gauss's recursive strategy:
	- Place the queens on the board one row at a time starting from the top.
	- To place the $r$th queen in the $r$th row, try all $n$ squares in the row from left to right using a loop. If a square is being attacked by an earlier queen, then ignore the square.
	- If the square is a valid placement, then we temporarily place a queen on there and recursively check later rows for a consistent placement of the queens.
- Pseudocode:
```
PlaceQueens(Q[1..n], r):
	if r = n + 1:
		print Q[1..n]
	else:
		for j = 1 to n:
			legal = True
			for i = 1 to r - 1:
				if (Q[i]=j) or (Q[i]=j+r-1) or (Q[i]=j-r+i):
					legal = False
			if legal:
				Q[r] = j
				PlaceQueens(Q[1..n], r+1)
```
- The algorithm recursively enumerates through *all* complete $n$-queens solutions that are consistent with a given partial solution.
- We represent the positions of the queens with the array $Q[1..n]$ where $Q[i]$ indicates which square in row $i$ contains a queen.
- $r$ is the index of the first empty row and $Q[1..r-1]$ contains the positions of all the queens before $r$.
- The outer for-loop checks for all possible placements of a queen in the row $r$.
- The inner for-loop checks if a temporary candidate placement on row $r$ is consistent with the the queens that are already placed on the first $r-1$ rows.
- Our initial call of the algorithm to solve the entire tree would be `PlaceQueens(Q[1..n], 1)`.
- N-Queens solution as a recursion tree for the n=4:
  ![[Pasted image 20230524122438.png]]
- Each node is a recursive subproblem and also a legal partial solution.
- Each level is the row being examined (the root is r=0 and the bottom leaves are r=4)
- The edges correspond to recursive calls.
- The leaves are the partial solutions that cannot be extended because there are no more valid placements of queens with the current board (either because every possible placement is attacked by previous queens or all the rows are already filled).
# 2.2 Game Trees

# 2.3 Subset Sum

# 2.4 The General Pattern

# 2.5 Text Segmentation (Interpunctio Verborum)

# 2.6 Longest Increasing Subsequence

# 2.7 Longest Increasing Subsequence, Take 2

# 2.8 Optimal Binary Search Trees

