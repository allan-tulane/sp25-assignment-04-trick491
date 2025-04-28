# CMPS 2200 Assignment 5
## Answers

**Name:**_________Patrick Johnson________________


- **1a.**
The maximum depth of a d-ary heap with n nodes is about log_d n, since each level can have d times more nodes than the previous one.


- **1b.**
Insert takes O(log_d n) work to swap up to the root, while delete-min takes O(d log_d n) work because it compares d children at each of log_d n levels.


- **1c.**
Using a d-ary heap, Dijkstra's algorithm takes O((d |V| + |E|) log |V| / log d) work, combining |V| delete-mins and |E| inserts.



- **1d.**
To get O(|E|) running time when |E| = |V|^(1+ε), choose d ≈ |V|^ε / log |V|, balancing the work terms.



- **2a.**
For the graph (0→1: -2, 0→2: 2, 1→2: 1), APSP(i,j,k) values are: k=0: direct edges; k=1: 0→2 becomes -1 via 1; k=2: no further improvements.




- **2b.**
APSP(i,j,2) = min(APSP(i,j,1), APSP(i,2,1) + APSP(2,j,1)), considering paths through vertex 2, but it needs APSP with vertex 2, not just k=0 and k=1.





- **2c.**
APSP(i,j,k) = min(APSP(i,j,k-1), APSP(i,k,k-1) + APSP(k,j,k-1)), choosing between not using vertex k or using it as an intermediate.



- **2d.**
There are O(n^3) subproblems (i,j,k triples), each taking O(1) work with memoization, so total work is O(n^3).



- **2e.**
The DP algorithm (O(|V|^3)) beats Johnson’s (O(|V| |E| log |E|)) in dense graphs where |E| ≈ |V|^2, as it avoids the log factor.


- **3a.**
No, MST minimizes total weight but MMET minimizes the maximum edge weight, so MST might include a heavy edge that MMET avoids.


- **3b.**
Compute the MST, then for each MST edge, replace it with the smallest non-MST edge that reconnects the tree, and pick the tree with the next lowest total weight.


- **3c.**
The algorithm takes O(|V| |E|) work, from computing the MST in O(|E| log |V|) and checking |V| replacements each costing O(|E|).



