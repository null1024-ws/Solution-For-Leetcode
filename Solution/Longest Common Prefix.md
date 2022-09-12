### Solution 1 Transverse Scan
``` C++
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        int strsSize = strs.size();
        string res;
        int temp = 200;
        for(int i = 0;i < strsSize - 1;++i) {
            int checkSize = checkCommon(strs[i],strs[i + 1]).size();
            if(checkSize == 0) {
                return "";
            }
            temp = min(temp,checkSize);
        }
        res = strs[0].substr(0,temp);
        return res;
    }
    string checkCommon(string str1, string str2) {
        string res;
        unsigned long size = min(str1.size(), str2.size());
        for(int i = 0;i < size;++i) {
            if(str1[i] == str2[i]) {
                res += str1[i];
            }
            else{
                break;
            }
        }
        return res;
    }
};
```
### Divide and Conquer
``` C++
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        if (!strs.size()) {
            return "";
        }
        else {
            return longestCommonPrefix(strs, 0, strs.size() - 1);
        }
    }
    string longestCommonPrefix(vector<string>& strs, int start, int end) {
        if(start == end) {
            return strs[start];
        }
        else {
            int mid = (start + end) / 2;
            //divide and conquer
            string lcpLeft = longestCommonPrefix(strs, start, mid);
            string lcpright = longestCommonPrefix(strs, mid + 1, end);
            return commonPrefix(lcpLeft, lcpright);
        }
    }
    string commonPrefix(const string& lcpLeft, const string& lcpright) {
        int count = min(lcpLeft.size(), lcpright.size());
        for(int i = 0;i < count;++i) {
            if(lcpLeft[i] != lcpright[i]) {
                return lcpLeft.substr(0, i);
            }
        }
        return lcpLeft.substr(0, count); 
    }
};
```
