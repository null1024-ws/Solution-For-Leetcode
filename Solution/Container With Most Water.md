``` C++
class Solution {
public:
    int maxArea(vector<int>& height) {
        int waterVolume = 0;
        int left = 0, right = height.size() - 1;
        while(left < right) {
            int temp = (right - left) * min(height[left], height[right]);
            waterVolume = max(waterVolume, temp);
            if(height[left] < height[right]) {
                ++left;
            }
            else {
                --right;
            }
        }
        return waterVolume;     
    }
};
```
