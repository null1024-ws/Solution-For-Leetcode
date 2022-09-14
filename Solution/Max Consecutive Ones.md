``` C++
class Solution {
public:
    int findMaxConsecutiveOnes(vector<int>& nums) {
        int n = nums.size();
        int slow = -1;
        int check = 0;
        for(int fast = 0;fast < n;++fast) {
            if(nums[fast] != 1) {
                slow = fast;
            }
            check = max(check, fast - slow);
        }
        return check;
    }
};
```
