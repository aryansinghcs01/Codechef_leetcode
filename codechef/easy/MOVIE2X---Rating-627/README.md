# MOVIE2X - Rating 627

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)

## Problem

_Description not available._

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-10-10T13:19:50.408Z  

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

[View on CodeChef](https://www.codechef.com/problems/MOVIE2X)