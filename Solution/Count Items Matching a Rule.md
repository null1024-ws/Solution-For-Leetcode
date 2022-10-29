``` C++
class Solution {
public:
    int countMatches(vector<vector<string>>& items, string ruleKey, string ruleValue) {
        unordered_map<string, int> map = {{"type", 0}, {"color", 1}, {"name", 2}};
        int count = 0;
        int index = map[ruleKey];
        int n = items.size();
        for(int i = 0;i < n;++i) {
            if(items[i][index] == ruleValue) {
                count++;
            }
        } 
        return count;
    }
};
```
