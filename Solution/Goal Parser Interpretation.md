``` C++
class Solution {
public:
    string interpret(string command) {
        string res;
        for(int i = 0;i < command.size();++i) {
            if(command[i] == 'G') {
                res += 'G';
            }
            else if (command[i] == '(' && command[i + 1] == 'a') {
                res += "al";
                i = i + 3;
            }
            else if (command[i] == '(' && command[i + 1] == ')'){
                res += 'o';
                i = i + 1;
            }
        }
        return res;
    }
};
```
