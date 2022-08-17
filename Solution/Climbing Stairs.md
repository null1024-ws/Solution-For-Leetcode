``` C++
    //动态规划步骤
    //1. 确定dp[]含义以及下标
    //2. 递推公式
    //3. 初始化dp数组
    //4. 确定遍历顺序
    //5. 打印dp数组（用于debug）
class Solution {
public:
    int climbStairs(int n) {
        //dp[1] = 1, dp[2] = 2;
        //dp[i] = dp[i - 1] + dp[i - 2];
        int dp[46];
        dp[1] = 1;
        dp[2] = 2;
        for(int i = 3; i < n + 1;++i) {
            dp[i] = dp[i - 1] + dp[i - 2];
        }
        return dp[n];
    }
};
```
