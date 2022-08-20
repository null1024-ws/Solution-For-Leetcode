``` C++
//从dp[0][j],dp[i][0]开始初始化
class Solution {
public:
    int uniquePathsWithObstacles(vector<vector<int>>& obstacleGrid) {
        int m = obstacleGrid.size();
        int n = obstacleGrid[0].size();
        vector<vector<int>>dp(m,vector<int>(n,0));
        // 定义 dp 数组并初始化第 1 行和第 1 列
        for(int i = 0;i < m && obstacleGrid[i][0] == 0;++i) {
            dp[i][0] = 1;
        }
        for(int j = 0;j < n && obstacleGrid[0][j] == 0;++j) {
            dp[0][j] = 1;
        }
        //建立递推公式并遍历dp数组
        for(int i = 1;i < m;++i) {
            for(int j = 1;j < n;++j) {
                if(obstacleGrid[i][j] == 0) { // 与LeetCode 62不同之处
                    dp[i][j] = dp[i - 1][j] + dp[i][j - 1];
                }
            }
        }
        return dp[m - 1][n - 1];
    }  
};
```
