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
class Solution {
public:
    int strStr(string haystack, string needle) {
        int m = haystack.size(), n = needle.size();
        int next[n + 1];
        next[0] = -1;
        int i = 0, j = -1;
        while (i < n) {
		    if (j == -1 || needle[i] == needle[j]) {
			    ++i;
			    ++j;
			    next[i] = j;
		    }	
		    else
			    j = next[j];
	    }
        i = 0; 
	    j = 0;

	    while (i < m && j < n) {
		    if (j == -1 || haystack[i] == needle[j]) {
			    i++;
           		j++;
		    }
	 	    else 
           		j = next[j];
    	    }

        if (j == n)
            return i - j;
        else 
            return -1;
    }
};
```
