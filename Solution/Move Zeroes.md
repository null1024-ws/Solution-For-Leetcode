``` C++
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        unsigned long n = nums.size();
        int slow = 0;
        for(int fast = 0;fast < n;++fast) {
            if(nums[fast] != 0) {
                nums[slow++] = nums[fast];
            }
        }
        for(;slow < n;++slow) {
            nums[slow] = 0;
        }
    }
};
```
