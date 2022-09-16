``` C++
class Solution {
public:
    string reverseWords(string s) {
        int n = s.size();
        int i = 0, j = 1;
        string res;
        s = s + ' ';
        while(j <= n) {
            int count = 1;
            if(s[j] == ' ') {
                string temp = s.substr(i, j - i);
                for(int k = temp.size() - 1;k >= 0;--k) {
                    res += temp[k];
                    count--;
                }
                if(count <= 0 && j != n) {
                    res += ' ';
                }
                i = j + 1;
            }
            j++;
        }
        return res;
    }
};
```
