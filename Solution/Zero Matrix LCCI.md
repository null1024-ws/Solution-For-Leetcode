``` C++
class Solution {
public:
    void setZeroes(vector<vector<int>>& matrix) {
        auto mirrorMatrix = matrix;
        int M = matrix.size();
        int N = matrix[0].size();
        for(int i = 0;i < M;++i) {
            for(int j = 0;j < N;++j) {
                if(mirrorMatrix[i][j] == 0) {
                    for(int k = 0;k < M;++k) {
                        matrix[k][j] = 0;
                    }
                    setVetor(matrix[i]);
                }
            }
        }
    }
    void setVetor(vector<int>& vec) {
        for(auto& i : vec) {
            i = 0;
        }
    }
};
```
