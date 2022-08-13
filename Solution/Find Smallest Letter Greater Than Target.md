``` C++
class Solution {
public:
    char nextGreatestLetter(vector<char>& letters, char target) {
        int lettersSize = letters.size();
        for(int i = 0;i < lettersSize;i++) {
            if(letters[i] > target) {
                return letters[i];
                break;
            }
        }
        return letters[0];
     }
};
```
