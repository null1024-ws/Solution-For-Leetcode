``` C++
class Solution {
public:
    int minOperations(vector<int>& nums) {
        int n = nums.size(), res = 0;
        int temp = nums[0];
        for(int i = 1;i < n;++i) {
            if(nums[i] <= temp) {
                res += (temp + 1 - nums[i]);
                nums[i] = temp + 1;
            } 
                temp = nums[i];
        }
        return res;
    }
};
```
