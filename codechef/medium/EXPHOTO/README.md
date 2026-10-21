# EXPHOTO

![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)

## Problem

### Exun Photo

You are given a permutation $P$ of the integers $[1, N]$, and an integer $K$.

You can perform the following operation as many times as you want (possibly $0$):

- Choose $(L, R)$ such that $(R - L + 1) \le K$ and $1 \le L \le R \le N$.
- Let $t$ denote the index of the maximum element in $P_i$ for $L \le i \le R$.
- The element $P_t$ is removed, and reinserted just before $P_L$.
- Thus, the segment $P[L, R]$ becomes $P_t P_{L} \ldots P_{t - 1} P_{t + 1} \ldots P_R$.

Find the minimum number of operations needed to make permutation $P = (N, N - 1, \ldots, 1)$, i.e. sorted descending order.

If it is not possible, output $-1$ instead.

### Input Format
- The first line of input contains a single integer $T$, denoting the number of test cases.
- Each test case consists of two lines of input. The first line of each test case contains two space-separated integers $N$ and $K$. The second line contains $N$ space-separated integers $P_1, P_2, \ldots, P_N$.
### Output Format

For each test case, output on a new line the minimum number of operations or $-1$ if not possible.

### Constraints
- $1 \leq T \leq 10^5$
- $1 \leq N \leq 2 \cdot 10^5$
- $1 \leq K \leq 2 \cdot 10^5$
- $P$ is a permutation of $1, 2, \ldots, N$.
- The sum of $N$ over all test cases does not exceed $2 \cdot 10^5$.
### Sample 1:
Input
Output

```
3
5 3
3 1 2 5 4
4 4
4 3 2 1
3 2
1 2 3

```

```
5
0
3
```

### Explanation:

Test case $1$: One optimal sequence of operations, each written as $[l, r]$:

$[2, 4]$: $(3, 1, 2, 5, 4) \to (3, 5, 1, 2, 4)$ $[1, 2]$: $(3, 5, 1, 2, 4) \to (5, 3, 1, 2, 4)$ $[3, 5]$: $(5, 3, 1, 2, 4) \to (5, 3, 4, 1, 2)$ $[2, 3]$: $(5, 3, 4, 1, 2) \to (5, 4, 3, 1, 2)$ $[4, 5]$: $(5, 4, 3, 1, 2) \to (5, 4, 3, 2, 1)$

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-10-21T15:10:10.615Z  

```c_cpp

#include <bits/stdc++.h>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int T;
    cin >> T;

    while (T--) {
        int N, K;
        cin >> N >> K;

        vector<int> P(N);
        for (int i = 0; i < N; i++) {
            cin >> P[i];
        }

        if (K == 1) {
            bool sorted = true;

            for (int i = 1; i < N; i++) {
                if (P[i - 1] < P[i]) {
                    sorted = false;
                    break;
                }
            }

            cout << (sorted ? 0 : -1) << '\n';
            continue;
        }

        vector<int> bit(N + 1, 0);

        auto query = [&](int idx) {
            int sum = 0;
            while (idx > 0) {
                sum += bit[idx];
                idx -= idx & -idx;
            }
            return sum;
        };

        auto update = [&](int idx) {
            while (idx <= N) {
                bit[idx]++;
                idx += idx & -idx;
            }
        };

        long long ans = 0;

        for (int x : P) {
            int cnt = query(x - 1);
            ans += (cnt + K - 2) / (K - 1);
            update(x);
        }

        cout << ans << '\n';
    }

    return 0;
}

```

---

[View on CodeChef](https://www.codechef.com/problems/EXPHOTO)