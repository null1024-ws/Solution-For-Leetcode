``` C++
class Solution {
public:
    vector<int> finalPrices(vector<int>& prices) {
        vector<int> res;
        int n = prices.size();
        for(int i = 0;i < n;++i) {
            int checkNumber = 0;
            for(int j = i + 1;j < n;++j) {
                int minusNumber = prices[j] - prices[i];
                 if(minusNumber <= 0) {
                    checkNumber = prices[j];
                    break;
                }
            }
            res.push_back(prices[i] - checkNumber);
        }
        return res;
    }
};
```
