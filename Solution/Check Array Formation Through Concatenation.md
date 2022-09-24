``` C++
class Solution {
public:
    bool canFormArray(vector<int>& arr, vector<vector<int>>& pieces) {
        int m = arr.size();
        int n = pieces.size();
        for(int i = 0;i < n;++i) {
            if(pieces[i].size() >= 1) {
                if(!check(arr, pieces[i])) {
                    return false;
                }
            }
        }
        return true;
    }
    bool check(vector<int>& vec1, vector<int>& vec2) {
        int m = vec1.size();
        int n = vec2.size();
        for(int i = 0;i < m + 1 - n;++i) {
            int j = 0;
            while(j < n && vec1[i + j] == vec2[j]) {
                j++;
            }
            if(j == n) {
                return true;;
            }
            //return -1;
        }
        return false;
    }
};
```
