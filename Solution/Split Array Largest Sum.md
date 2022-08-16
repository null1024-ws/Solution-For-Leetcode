
``` C++
class Solution {
public:
    //二分查找 贪心算法
    //由题目，将数组划分为m个非空的连续子数组，然后确定这些子数组各自和的最大值的最小值
    //显然这个最终返回结果一定在[max(nums),sum(nums)]中，因此二分过程中的left、right
    //确定了下来
    //我们不妨假设这个要返回的最大值不超过mid(即不超过)，利用贪心算法从前到后遍历数组
    //用sum 表示当前分割子数组的和，cnt 表示已经分割出的子数组的数量(包括当前子数组)
    //如果我们设置的 mid 过大，那么形成的组数太少，不符合m组的题意，应当减小mid
    //mid过小，则分成的组数过多，则应当增加 mid;显然只有控制cnt<=m时，我们不断二分确定好的
    //数组区间，直到找到结果
    //注意事项：如果某个数组各自和的最大值 恰恰好使得分割数为 m ，此时不能放弃搜索，
    //因为我们要使得这个最大值 最小化，此时还应该继续尝试缩小这个 数组各自和的最大值 ，
    //使得分割数超过 m ，超过 m 的最后一个使得分割数为 m 的 数组各自和的最大值
    // 就是我们要找的 最小值。
    // 以题目中的[7,2,5,3,8]为例子，m = 2
    // 由刚才的分析搜索区间[8,25]
    //设置 数组各自和的最大值 为 20，此时分割依然是 [7, 2, 5, | 10, 8]，m = 2；
    //设置 数组各自和的最大值 为 19，此时分割依然是 [7, 2, 5, | 10, 8]，m = 2；
    //设置 数组各自和的最大值 为 18，此时分割依然是 [7, 2, 5, | 10, 8]，m = 2；
    //设置 数组各自和的最大值 为 17，此时分割就变成了 [7, 2, 5, | 10, | 8]，这时 m = 3
    //这就是“=”的处理

    //check函数，控制cnt<=m
    bool check(vector<int>& nums, int m, int target) {
        int cnt = 1;
        long long sum = 0;
        for(int i = 0;i < nums.size();++i) {
            if(sum + nums[i] > target) {
                cnt++;
                sum = nums[i];
            }
            else {
                sum += nums[i];
            }
        }
        return cnt <= m;
    }
    int splitArray(vector<int>& nums, int m) {
        long long int left = 0, right = 0;
        for (int i = 0; i < nums.size(); i++) {
            right += nums[i];
            if (left < nums[i]) {
                left = nums[i];
            }
        }
        while(left < right) {
            long long int mid = (left + right) >> 1;
            if (check(nums, m, mid)) {
                right = mid;
            } else {
                left = mid + 1;
            }
        }
        return left;
    }

};
```
