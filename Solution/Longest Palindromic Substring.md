``` C++
class Solution {
public:
    string longestPalindrome(string s) {
        string res;
        //中心扩展思想
        for(int i = 0;i < s.size();++i) {
            //aba 
            int left1 = i, right1 = i;
            while(left1 >= 0 && right1 < s.size() && s[left1] == s[right1]) {
                left1--;
                right1++; 
            }
            if(res.size() < right1 - left1 - 1) {
                res = s.substr(left1 + 1,right1 - left1 - 1); // 注意left1 + 1，因为while循环多减了一次
            }
            //abba
            int left2 = i, right2 = i + 1;
            while(left2 >= 0 && right2 < s.size() && s[left2] == s[right2]) {
                left2--;
                right2++;
            }
            if(res.size() < right2 - left2 - 1) {
                res = s.substr(left2 + 1,right2 - left2 - 1);
            }
        }
        return res;
    }
};
```
