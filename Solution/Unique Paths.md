### Solution 1
``` C++
class Solution {
public:
    int uniquePaths(int m, int n) {
        //dp[m][n] 表示m✖n方格时机器人从起点到终点的不同路径条数
        //dp[1][] = dp[][1] = 1;
        int dp[m + 1][n + 1];
        for(int i = 1;i <= n;++i) {
            dp[1][i] = 1;
        }
        for(int j = 1;j <= m;++j) {
            dp[j][1] = 1;
        }
        for(int j = 2;j <= m;++j) {
            for(int i = 2;i <= n;++i) {
                dp[j][i] = dp[j - 1][i] + dp[j][i - 1];
            }
        }
        return dp[m][n];
    }
};
```
### Solution 2
``` C++
class Solution {
public:
    int uniquePaths(int m, int n) {
        long long ans = 1;
        for (int x = n, y = 1; y < m; ++x, ++y) {
            ans = ans * x / y;
        }
        return ans;
    }
};
```
