``` C++
class Solution {
public:
    int partitionDisjoint(vector<int>& nums) {
        //5 3 0 8 6
        int n = nums.size();
        vector<int> Rmin(n, nums.back());
        for(int i = n - 2;i >= 0;i--) {
            Rmin[i] = min(Rmin[i + 1], nums[i]);
        }
        for(int j = 0, l = 0;j < n - 1;j++) {
            l = max(l, nums[j]);
            if(l <= Rmin[j + 1]) {
                return j + 1;
            }
        }
        return -1;
    }
};
```
