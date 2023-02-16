**# Pascal's Triangle**

**Question**:-

Given an integer numRows, return the first numRows of Pascal's triangle.
```
      1
    1   1
  1   2   1
 1   3   3  1
1   4  6  4   1
```


Example 1:
```
Input: numRows = 5
Output: [[1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1]]
```
Example 2:
```
Input: numRows = 1
Output: [[1]]
```


**Solution**
```c++
#include <bits/stdc++.h>
using namespace std;

class Solution
{
public:
    vector<vector<int>> generate(int numRows)
    {
        vector<vector<int>> ans(numRows);
        for (int i = 0; i < numRows; i++)
        {
            ans[i].resize(i + 1);
            for (int j = 0; j <= i; j++)
            {
                if (j == 0 || j == i)
                {
                    ans[i][j] = 1;
                }
                else
                {
                    ans[i][j] = ans[i - 1][j - 1] + ans[i - 1][j];
                }
            }
        }
        return ans;
    }
};

int main()
{
    Solution sb;
    int n;
    cout << "Enter The number that you need to rows: ";
    cin >> n;
    vector<vector<int>> rows = sb.generate(n);
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j <= i; j++)
        {
            cout << rows[i][j] << " ";
        }
        cout << endl;
    }
    return 0;
}
