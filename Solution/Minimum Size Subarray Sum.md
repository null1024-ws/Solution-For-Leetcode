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


```
