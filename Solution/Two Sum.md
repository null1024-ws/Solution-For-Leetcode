```C++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        std::unordered_map<int,int> hashtable;
        for(int i = 0;i < nums.size();i++) {
            int r = target - nums[i];
            if(hashtable.count(r)) {
                return{i,hashtable[r]};
            }
            hashtable[nums[i]] = i;
        }
        return{-1,-1};
    }
};
```
