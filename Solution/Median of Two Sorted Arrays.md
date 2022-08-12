```C++
class Solution {
public:
    double findMedianSortedArrays(vector<int>& nums1, vector<int>& nums2) {
        vector<double> connectedVector;
        for(int i = 0;i < nums1.size();++i) {
            connectedVector.push_back(nums1[i]);
        }
        for(int j = 0;j < nums2.size();++j) {
            connectedVector.push_back(nums2[j]);
        }
        sort(connectedVector.begin(), connectedVector.end());
        int mid = connectedVector.size() / 2;
        if(connectedVector.size() % 2 == 0) {
            return (connectedVector[mid] + connectedVector[mid - 1]) / 2;
        }
        return connectedVector[mid];
    }
};
```

