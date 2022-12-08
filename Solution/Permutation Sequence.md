``` C++
class Solution {
public:
    string getPermutation(int n, int k) {
        string res;
        vector<bool> flag(10,false);
        for(int i = 1;i <= n;++i) {
            int factorial = getNumber(n - i);
            for(int j = 1;j <= n;++j) {
                if(!flag[j]) {
                    if(k <= factorial) {
                        res += to_string(j);
                        flag[j] = true;
                        break;
                    }
                    k -= factorial;
                }
            }
        }
        return res;
    }
    int getNumber(int n) {
        if(n == 1 || n == 0) return 1;
        return n * getNumber(n - 1);
    }
}; 
```
