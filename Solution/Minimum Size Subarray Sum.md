### Solution 1 Sliding Window
``` C++
class Solution {
public:
    int minSubArrayLen(int s, vector<int>& nums) {
        int n = nums.size();
        if (n == 0) {
            return 0;
        }
        int ans = INT_MAX;
        int left = 0, right = 0;
        int sum = 0;
        while (right < n) {
            sum += nums[right];
            while (sum >= s) {
                ans = min(ans, right - left + 1);
                sum -= nums[left];
                left++;
            }
            right++;
        }
        return ans == INT_MAX ? 0 : ans;//判断
    }
};
```
### Solution 2 Preflix Sum
``` C++
class Solution {
public:
    int minSubArrayLen(int target, vector<int>& nums) {
        int n = nums.size();
        int ans = INT_MAX;
        vector<int> sum(n + 1, 0);
        for(int i = 1;i <= n;++i) {
            sum[i] = sum[i - 1] + nums[i - 1];
        }
        for(int i = 1;i <= n;++i) {
            int newTarget = target +sum[i - 1];
            auto bound = lower_bound(sum.begin(), sum.end(), newTarget);
            if (bound != sum.end()) {
                ans = min(ans, static_cast<int>((bound - sum.begin()) - (i - 1)));
            }
        }
        return ans ==INT_MAX ? 0 : ans;
    }
};
```
