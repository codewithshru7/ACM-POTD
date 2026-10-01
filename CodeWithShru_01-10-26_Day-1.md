# POTD Day 1

## Problem

**Codeforces 14A - Letter**

We are given a grid containing `.` and `*`. We have to find the smallest rectangle containing all the `*` characters and print it.

## Approach

First, I store the grid in a `vector<string>`.

Then I check the whole grid and find the first and last row and column where `*` is present.

I store these positions in `minRow`, `maxRow`, `minCol` and `maxCol`.

Finally, I print the part of the grid between these four boundaries.

## Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    int n, m;
    cin >> n >> m;

    vector<string> grid(n);

    for (int i = 0; i < n; i++) {
        cin >> grid[i];
    }

    int minRow = n;
    int maxRow = -1;
    int minCol = m;
    int maxCol = -1;

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < m; j++) {
            if (grid[i][j] == '*') {
                minRow = min(minRow, i);
                maxRow = max(maxRow, i);
                minCol = min(minCol, j);
                maxCol = max(maxCol, j);
            }
        }
    }

    for (int i = minRow; i <= maxRow; i++) {
        for (int j = minCol; j <= maxCol; j++) {
            cout << grid[i][j];
        }
        cout << '\n';
    }

    return 0;
}
```

## Accepted Proof

![Accepted Solution](day%201.png)
