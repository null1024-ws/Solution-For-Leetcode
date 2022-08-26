``` C++
class Solution {
public:
    bool isPalindrome(int x) {
        string res = to_string(x);
        int length = res.size();
        for(int i = 0; i < length / 2; i++) {
            if(res[i] != res[length - 1 - i]) {
                return false;
            }
        }
        return true;
    }
};
```
