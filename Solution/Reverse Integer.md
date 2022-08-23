## Solution 1
``` C++
class Solution {
public:
    int reverse(int x) {
        int res = 0;
        while(x != 0) {
            if(res > 0 && res > (INT_MAX - x % 10) / 10) return 0;
            if(res < 0 && res < (INT_MIN - x % 10) / 10) return 0;
            res = res * 10 + x % 10;
            x /= 10;
        }
        return res;
    }
};
```
## Solution 2
``` C++
class Solution {
public:
    int reverse(int x) {
        //利用溢出之后除以10≠直接返回0，但按照以下代码res仍然会报错
        //Java版本不会)
        //思路很好
        int res = 0;
        /* Java版本
        while(x) {
            int temp = res;
            res = res * 10 + x % 10;
            x /= 10;
            if(res / 10 != temp) return 0;
        }
        */
    }
};
```
