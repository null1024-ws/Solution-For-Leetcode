``` C++
class Solution {
public:
    string reverseWords(string s) {
        reverse(s.begin(), s.end());
        int size = s.size();
        int idx = 0;
        for(int start = 0;start < size;++ start) {
            if(s[start] != ' ') {
                if(idx != 0) {
                    s[idx ++] = ' ';
                }
                int end = start; //双指针
                while(end < size && s[end] != ' ') {
                    s[idx ++] = s[end ++];
                } //遍历
                reverse(s.begin() + idx - (end - start), s.begin() + idx);
                start = end;
            }
            s.erase(s.begin() + idx,s.end());
        }
        return s;
    }
};
```
