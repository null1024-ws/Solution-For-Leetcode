```C++
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        int maxLength = 0;
        unordered_map<char,int> hashtable;
        for(int i = 0,j = 0;i < s.size();i++) {
            hashtable[s[i]]++;
            while(hashtable[s[i]] > 1) {
                hashtable[s[j]]--;
                j++;
            }
            maxLength = max(maxLength,i - j + 1);
        }
        return maxLength;
    }
};
```
