### Solution 1
``` C++
class Solution {
public:
    bool arrayStringsAreEqual(vector<string>& word1, vector<string>& word2) {
        int n = word1.size(), m = word2.size();
        string res1, res2;
        for(int i = 0;i < n;++i) {
            res1 += word1[i];
        }
        for(int i = 0;i < m;++i) {
            res2 += word2[i];
        }
        return res1 == res2;
    }
};
```
### Solution 2
``` C++
class Solution {
public:
    bool arrayStringsAreEqual(vector<string>& word1, vector<string>& word2) {
        int p1 = 0, q1 = 0, i = 0,j = 0;
        int m = word1.size(), n = word2.size();
        while(p1 < m && q1 < n) {
            if(word1[p1][i] != word2[q1][j]) {
                return false;
            }
            i++;
            if(i == word1[p1].size()) {
                p1++;
                i = 0;
            }
            j++;
            if(j == word2[q1].size()) {
                q1++;
                j = 0;
            }
        }
        return (p1 == m && q1 == n);
    }
};
```
