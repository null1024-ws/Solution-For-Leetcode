``` C++
class Solution {
public:
    int maximumSwap(int num) {
        string numTostring = to_string(num);
        int n = numTostring.size();
        //从前往后遍历，如果第一位比后面的都大，则继续遍历到第二位 --> 借助flag
        //如果比后面的小，则遍历完剩余的字符串，将其与剩余最大的数字且尽可能最低位交换 --> 借助temp
        bool flag = true;
        int count = 0;
        for(int i = 0;i < n;++i) {
            int j = i + 1;
            while(j < n) {
                if(numTostring[i] < numTostring[j]) {
                    flag = false;
                    break;
                }
                j++;
            }
            char temp = '0';
            int num = 0;
            if(!flag) {
                //取最后遇到的temp，这样才能最大,这里是>=
                for(int k = i + 1;k < n;++k) {
                    if(numTostring[k] >= temp) {
                        temp = numTostring[k];
                        num = k;
                    }
                }
                swap(numTostring[i], numTostring[num]);
                break;
            }
        }
        return stoi(numTostring);
    }
};
```
