``` C++
class Solution {
public:
    string convert(string s, int numRows) {
        //少数情况
    if (numRows == 1 || numRows >= s.size()) {
        return s;
    }
    //计算column数目
    int checkNumber = s.size() % (2 * numRows - 2);
    int columnNumber = s.size() / (2 * numRows - 2) * (numRows - 1);
    if(checkNumber > numRows) {
        columnNumber += (checkNumber - numRows + 1);
    }
    else {
        columnNumber += 1;
    }
    //二维数组模拟
    std::vector<std::string> str(numRows,std::string(columnNumber,0));
    for(int i = 0,x = 0,y = 0;i < s.size();++i) {
        str[x][y] = s[i];
        if(i % (numRows * 2 - 2) < numRows - 1) { // 关键
            x++;
        }
        else {
            x--;
            y++;
        }
    }
    std::string res;
    for (auto &row : str) {
        for (char ch : row) {
            if (ch) {
                res += ch;
            }
        }
    }
    return res;
    }
};
`
