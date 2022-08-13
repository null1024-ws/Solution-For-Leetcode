``` C++
class Solution {
public:
    int search(vector<int>& nums, int target) {
        // 二分查找的前提要排序，可以找出断点
        int left = 0, right = nums.size() - 1;
        while(left < right) {
            int mid = left + (right - left) / 2;
            if(nums[mid] > nums[left]) {
                left = mid;
            }
            else {
                right = mid;
            }
        }
        int left1 = 0,right1 = left;
        while(left1 <= right1) {
            int mid = left1 + (right1 - left1) / 2;
            if(nums[mid] < target) {
                left1 = mid + 1;
            }
            else if(nums[mid] > target) {
                right1 = mid - 1;
            }
            else {
                return mid;
            }
        }
        int left2 = left + 1,right2 = nums.size() - 1;
        while(left2 <= right2) {
            int mid = left2 + (right2 - left2) / 2;
            if(nums[mid] < target) {
                left2 = mid + 1;
            }
            else if(nums[mid] > target) {
                right2 = mid - 1;
            }
            else {
                return mid;
            }
        }
        return -1;
    }
};

```
