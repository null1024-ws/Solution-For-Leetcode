``` C++
class Solution {
public:
    double trimMean(vector<int>& arr) {
        sort(arr.begin(), arr.end());
        int n = arr.size();
        int checkNumber = n * 0.05;
        double sum = 0;
        for(int i = checkNumber;i < n - checkNumber;++i) {
            sum += arr[i];
        }
        double ans = sum / double(n - 2 * checkNumber);
        return ans;
    }
};
```
