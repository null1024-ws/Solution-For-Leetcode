``` C++
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
        //  0 1 2 2 3 0 4 2
        // 2
        int n = nums.size();
        int slow = 0;//计数器
        for(int fast = 0;fast < n;++fast) {
            if(nums[fast] != val) {
                nums[slow] = nums[fast];
                slow++;
            }
        }
        return slow;
    }
};
```
