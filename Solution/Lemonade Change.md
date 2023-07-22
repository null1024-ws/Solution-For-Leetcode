``` C++
class Solution {
public:
    bool lemonadeChange(vector<int>& bills) {
        int five_num = 0, ten_num = 0;
        for (auto& bill: bills) {
            if(bill == 5) {
                five_num++;
            } else if (bill == 10) {
                if(five_num == 0) return false;
                five_num--;
                ten_num++;
            } else {
                if(five_num  > 0 && ten_num > 0) {
                    five_num--;
                    ten_num--;
                }
                else if(five_num >= 3) {
                    five_num -= 3;
                } else {
                    return false;
                }
            }
        }
        return true;
    }
};

```
