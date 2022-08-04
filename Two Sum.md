```c++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        std::unordered_map<int,int> hashtable;
        for(int i = 0;i < nums.size();i++) {
            //auto it = hashtable.find(target - nums[i]);
            int r = target - nums[i];
            if(hashtable.count(r)) {
                return{i,hashtable[r]};
            }
            //if(it != hashtable.end() && it->second != i) {
            //    return{i,it->second};
            //}
            hashtable[nums[i]] = i;
        }
        return{-1,-1};
    }
};
```


