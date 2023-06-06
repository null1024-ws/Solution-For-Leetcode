``` C++
class Solution {
public:
    int equalPairs(vector<vector<int>>& grid) {
        int n = grid.size();
        map<vector<int>, int> table;
        for(auto row : grid) {
            table[row]++;
        }
        int ans = 0;
        for(int j = 0;j < n;++j) {
            vector<int> arr;
            for(int i = 0;i < n;++i) {
                arr.emplace_back(grid[i][j]);
            }
            if(table.find(arr) != table.end()) {
                ans += table[arr];//可能会存在重复的列或行
            }
        }
        return ans;
    }
};
```
