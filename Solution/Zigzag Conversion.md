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
```

``` C++
class Solution {
public:
    string convert(string s, int numRows) {
        const int strSize = s.size();
        const int checkNumber = 2 * numRows - 2;
        if(numRows == 1 || numRows > strSize) {
            return s;
        }
        std::string res;
        for(int i = 0;i < numRows;++i) {
            if(i ==0 || i == numRows - 1) {
                for(int j = i;j < strSize;j = j + checkNumber) {
                    res += s[j];
                }
            }
        else {
            for(int j = i,k = checkNumber - j;j < strSize || k < strSize;j += checkNumber,k += checkNumber) {
                if(j < s.size()) res += s[j];
                if(k < s.size()) res += s[k];
            }
        }
    }
    return res;
    }
};
```
