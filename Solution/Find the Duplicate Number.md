``` C++
class Solution {
public:
    int findDuplicate(vector<int>& nums) {
        unordered_map<int,int> hashtable;
        for(int i = 0;i < nums.size();++i) {
            hashtable[nums[i]]++;
            if(hashtable[nums[i]] >= 2) {
                return nums[i];
            }
        }
        return 0;
    }
};

```
