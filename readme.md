## Examples

### n = 3
$\begin{bmatrix} 
  0 & 4 & 8 \\ 
  1 & 5 & 2 \\ 
  3 & 7 & 6 
\end{bmatrix}$

Quality: 25,
Cost: 1858,
Efficiency: 0.013455328310010764

### n = 4
$\begin{bmatrix} 
  8 & 6 & 9 & 3 \\ 
  1 & 13 & 5 & 15 \\ 
  2 & 14 & 0 & 4 \\ 
  10 & 12 & 11 & 7 
\end{bmatrix}$

Quality: 49,
Cost: 12615,
Efficiency: 0.003884264764169639


### n - 5
$\begin{bmatrix} 
  1 & 13 &  9 & 10 &  3 \\ 
  4 &  0 & 16 & 12 &  5 \\ 
  7 &  8 &  2 & 14 & 15 \\ 
 22 & 18 & 17 & 23 & 20 \\ 
  6 & 11 & 21 & 19 & 24 
\end{bmatrix}$

Quality: 61,
Cost: 86423,
Efficiency: 0.0007058306237922776

### n = 6
$\begin{bmatrix} 
  1 & 3 & 9 & 4 & 0 & 6 \\ 
  8 & 27 & 2 & 16 & 5 & 12 \\ 
  7 & 19 & 14 & 15 & 10 & 24 \\ 
  13 & 28 & 32 & 17 & 11 & 20 \\ 
  25 & 26 & 21 & 23 & 18 & 29 \\ 
  31 & 33 & 34 & 35 & 22 & 30 
\end{bmatrix}$

Quality: 67,
Cost: 67411,
Efficiency: 0.0009939030721988994

### Note for review
1. For the compute_distance function, I combined two heuristics to improve the algorithm: Manhattan distance, which measures the effective distance to the solution, and the count of misplaced tiles, which highlights conflicts where tiles block each other’s paths. This combination provides a balanced estimate, helping the algorithm prioritize states closer to the goal.
    
    A weighted sum of the two contributes can be done, but I noticed that the performance are better considering the sum with weights equal to 1.  

2. To improve the algorithm's performance, states are prioritized by their __f__ and, in case of ties, by their __g__ (the depth in this case). Ordering by __f__ ensures the algorithm explores the most promising states first, while considering __g__ helps break ties by preferring states found earlier (with smaller depth) because they could represent a less complex path.

3. If the __rand_moves__ value is too high, the puzzle might become overly mixed, causing the computational time to solve it to grow exponentially. Therefore, I chose a __rand_moves__ value that balances mixing complexity and performance.