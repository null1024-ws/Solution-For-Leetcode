``` C++
class Solution {
public:
    vector<int> findDiagonalOrder(vector<vector<int>>& mat) {
        vector<int> res;
        int m = mat.size();
        int n = mat[0].size();
        int matCapacity = m * n;
        int x = 0, y = 0;
        for(int i = 0;i < matCapacity;++i) {
            res.push_back(mat[x][y]);
            if((x + y) % 2 == 0) {
                if(y == (n - 1)) {
                    x++;
                }
                else if(x == 0) {
                    y++;
                }
                else {
                    x--;
                    y++;
                }
            }
            else {
                if(x == (m - 1)) {
                    y++;
                }
                else if(y == 0) {
                    x++;
                }
                else {
                    x++;
                    y--;
                }
            }
        }
        return res;
    }
};
```
