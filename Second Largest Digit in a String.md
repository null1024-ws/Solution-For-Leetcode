``` C++
class Solution {
public:
    int secondHighest(string s) {
        int first = -1, second = -1;
        for(auto& i : s) {
            if(isdigit(i)) {
                int number = i - '0';
                if(number > first) {
                    second = first;
                    first = number;
                }
                else if(number > second && number < first) {
                    second = number;
                }
            }
        }
        return second;
    }
};
```
