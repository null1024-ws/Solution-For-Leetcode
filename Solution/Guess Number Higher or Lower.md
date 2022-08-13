``` C++
/** 
 * Forward declaration of guess API.
 * @param  num   your guess
 * @return 	     -1 if num is lower than the guess number
 *			      1 if num is higher than the guess number
 *               otherwise return 0
 * int guess(int num);
 */

class Solution {
public:
    int guessNumber(int n) {
        int left = 1;
        int right = n;
        while(left <= right) {
            int num = left + (right - left) / 2;
            if(guess(num) == 0) {
                return num;
            }
            else if(guess(num) == 1) {
                left = num + 1;
            }
            else {
                right = num - 1;
            }
        }
        return -1;
    }
};





```
