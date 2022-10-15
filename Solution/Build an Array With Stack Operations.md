``` C++
class Solution {
public:
    vector<string> buildArray(vector<int>& target, int n) {
        std::vector<int> list;
        std::vector<std::string> res;
        for(int i = 0;i < n;++i) {
            list.push_back(i + 1);
        }
        int j = 0;
        for(int i = 0; i < n;++i) {
            if(list[i] == target[j]) {
                res.emplace_back("Push");
                j++;
            }
            else {
                res.emplace_back("Push");
                res.emplace_back("Pop");
            }
            if(j == target.size()) {
                break;
            }
        }
            return res;
    }
};
```
