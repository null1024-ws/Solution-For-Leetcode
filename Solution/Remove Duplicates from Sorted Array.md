### Solution 1
``` C++
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        nums.erase(std::unique(nums.begin(), nums.end()),nums.end());
        return nums.size();
    }
};
```
### Solution 2 Two Pointers
``` C++
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        int p = 0, q = 1;
        int n = nums.size();
        while(q < n) {
            if(nums[p] != nums[q]) {
                if(q > 1 + p) {
                    nums[p + 1] = nums[q];
                }
                p++;
            }
            q++;
        }
        return p + 1;
    }
};
```
