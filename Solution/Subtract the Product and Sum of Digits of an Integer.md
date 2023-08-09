### Solution 1 (stupid)
``` C++
class Solution {
public:
    int subtractProductAndSum(int n) {
        string str = to_string(n);
        int result, len = str.size();
        int sum = 0, multiply = 1;
        for(int i = 0;i < len;++i) {
            int temp = str[i] - '0';
            sum += temp;
            multiply *= temp;
        }
        result = multiply - sum;
        return result;
    }
};
```
### Solution 2
``` C++
class Solution {
public:
    int subtractProductAndSum(int n) {
        int m = 1, s = 0;
        while(n) {
            int x = n % 10;
            n /= 10;
            m *= x;
            s += x;
        }
        return m - s; 
    }
};
```
