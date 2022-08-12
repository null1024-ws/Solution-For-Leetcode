```C++
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        int maxLength = 0;
        unordered_map<char,int> hashtable;
        // 双指针法
        // 遍历字符串，利用哈希表存放字符出现次数，当某个字符次数大于一时，i保持不变，j逐渐靠近i，直到[j,i]区间内没有重复字符
        //最终取得最大区间数值，即i-j+1；
        for(int i = 0,j = 0;i < s.size();i++) {
            hashtable[s[i]]++;
            while(hashtable[s[i]] > 1) {
                hashtable[s[j]]--; 
                j++; // hashtable[s[j++]]--
            }
            maxLength = max(maxLength,i - j + 1);
        }
        return maxLength;
    }
};
```
