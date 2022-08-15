``` C++
class Solution {
public:
    int getNumber(vector<int>&nums,int mid) {
        int res = 0;
        for(int i = 0,j = 1;j < nums.size();j++) {
            while(i < j && nums[j] - nums[i] > mid) {
                i++;
            }
            res += j - i;
        }
        return res;    
    }
    int smallestDistancePair(vector<int>& nums, int k) {
        sort(nums.begin(), nums.end());
        int n = nums.size();
        int left = 0, right = nums[n - 1] - nums[0];
        while(left < right) {
            int mid = (left + right) >> 1;
            if(getNumber(nums,mid) >= k) {
                right = mid;
            }
            else {
                left = mid + 1;
            }
        }
        return left;
    }
};
```
