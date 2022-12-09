``` C++
class Solution {
public:
    bool isPowerOfFour(int n) {
        if(n < 4) return n == 1;
        return (n % 4 == 0) ? isPowerOfFour(n / 4) : false;  
    }
};
```
