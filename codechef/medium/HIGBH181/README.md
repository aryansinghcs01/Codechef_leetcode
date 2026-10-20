# HIGBH181

![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)

## Problem

### Implementation - Adjacency Matrix

In this section, we will check out how to implement the adjacency matrix we discussed.

The code given on the right forms the adjacency matrix for the tree given above. Notice how the edges are taken as input and run the code to see the matrix.

### Input Format
- The first line of input will contain a single integer $N$, denoting the number of nodes in the Tree.
- Then the next N - 1 lines contains two numbers $u_i$ and $v_i$ denoting the i-th edge of the Tree.
### Output Format

Output the final adjacency matrix.

### Sample 1:
Input
Output

```
6
0 1
0 2
1 3
1 4
2 5
```

```
  
```

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-10-20T10:39:24.030Z  

```c_cpp
#include <stdio.h>

int main() {
    int N;
    scanf("%d", &N);

    int adj[100][100] = {0};

    for (int i = 0; i < N - 1; i++) {
        int u, v;
        scanf("%d %d", &u, &v);

        adj[u][v] = 1;
        adj[v][u] = 1;
    }

    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            printf("%d", adj[i][j]);

            if (j < N - 1)
                printf(" ");
        }
        printf("\n");
    }

    return 0;
}
```

---

[View on CodeChef](https://www.codechef.com/problems/HIGBH181)