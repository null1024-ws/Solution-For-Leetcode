``` C++
//Sliding Window
class Solution {
public:
    vector<int> decrypt(vector<int>& code, int k) {
        int n = code.size();
        vector<int> res(n);
        if(k == 0) {
            return res;
        }
        //5 7 1 4
        int l = k > 0 ? 1 : n + k;
        int r = k > 0 ? k : n - 1;
        int w = 0;
        for (int i = l % n; i <= r % n; i++) {
            w += code[i];
        }
        for (int i = 0; i < n; i++) {
            res[i] = w;//填入数值
            r = (r + 1) % n;//利用模运算映射
            w -= code[l];//移除窗口最左边元素
            w += code[r];//加上右边元素
            l = (l + 1) % n;
        }
        return res;
    }
};
```
