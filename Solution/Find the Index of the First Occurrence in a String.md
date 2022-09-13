### Solution 1 Brute Force
``` C++
class Solution {
public:
    int strStr(string haystack, string needle) {
        int m = haystack.size(), n = needle.size();
        if(n == 0 || n > m) {
            return -1;
        }
        for(int i = 0;i < m + 1 - n;++i) {
            int j = 0;
            while(j < n && haystack[i + j] == needle[j]) {
                j++;
            }
            if(j == n) {
                return i;
            }
            //return -1;
        }
        return -1;
    }
};
```
### Solution 2 KMP Algorithm
``` C++

```
