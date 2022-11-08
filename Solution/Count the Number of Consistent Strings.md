``` C++
class Solution {
public:
    int countConsistentStrings(string allowed, vector<string>& words) {
        map<int,int> table;
        for(auto& s : allowed) {
            table[s - 'a'] = 1;
        }
        int count = 0, n = words.size();
        auto check = [&](string& str) {
            for(auto& c : str) {
                if(!table[c - 'a']) return false;
        }
            return true;
        };
        for(int i = 0;i < n;++i) {
            if(check(words[i])) {
                count++;
            }
        }
        return count;
    }
};
```
