``` C++
class Solution {
public:
    bool isFlipedString(string s1, string s2) {
        int m = s1.size(), n = s2.size();
        if (m != n) {
            return false;
        }
        if (n == 0) {
            return true;
        }
        for (int i = 0; i < n; i++) {
            bool flag = true;
            for (int j = 0; j < n; j++) { //轮转位数
                if (s1[(i + j) % n] != s2[j]) {
                    flag = false;
                    break;
                }
            }
            if (flag) {
                return true;
            }
        }
        return false;
    }
};
```
