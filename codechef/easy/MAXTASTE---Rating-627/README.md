# MAXTASTE - Rating 627

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)

## Problem

### Maximise the Tastiness

Chef is making a dish that consists of exactly two ingredients. He has four ingredients $A, B, C$ and $D$ with tastiness $a, b, c,$ and $d$ respectively. He can use either $A$ or $B$ as the first ingredient and either $C$ or $D$ as the second ingredient.

The tastiness of a dish is the sum of tastiness of its ingredients. Find the  **maximum**  possible tastiness of the dish that the chef can prepare.

### Input Format
- The first line of input will contain a single integer $T$, denoting the number of test cases.
- The first and only line of each test case contains four space-separated integers $a, b, c,$ and $d$ — the tastiness of the four ingredients.
### Output Format

For each test case, output on a new line the maximum possible tastiness of the dish that chef can prepare.

### Constraints
- $1 \leq T \leq 100$
- $1 \leq a, b, c, d \leq 100$
### Sample 1:
Input
Output

```
2
3 5 6 2
16 15 5 4

```

```
11
21
```

### Explanation:

 **Test case $1$:**  Chef can prepare a dish with ingredients $B$ and $C$ with a tastiness of $5+6=11$.

 **Test case $2$:**  Chef can prepare a dish with ingredients $A$ and $C$ with a tastiness of $16+5=21$.

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-10-10T13:19:31.320Z  

```c_cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	int t;
	cin>>t;
	while(t--){
	    int a,b,c,d;
	    cin>>a>>b>>c>>d;
	    int fst=max(a,b);
	    int scnd=max(c,d);
	    
	    cout<<fst+scnd<<endl;
	}

}

```

---

[View on CodeChef](https://www.codechef.com/problems/MAXTASTE)