``` C++
class Solution {
public:
    int integerBreak(int n) {
    //dp递推公式
    //当 i >= 2 时，假设对正整数 i 拆分出的第一个正整数是 j (j<i)
    //则以下两种方案：
    //将 i拆分成和i-j的和，且i-j不再拆分成多个正整数，此时的乘积是 j×(i−j)
    //将i拆分成j和i-j的和，且i-j继续拆分成多个正整数，此时的乘积是j×dp[i−j]。

        vector<int> dp(n + 1);
        for(int i = 2;i <= n;++i) {
            for(int j = 1;j < i;++j) {
                dp[i] = max(dp[i], max(j * (i - j),  dp[i - j] * j));
            }
        }
        return dp[n];
    }
};
```
