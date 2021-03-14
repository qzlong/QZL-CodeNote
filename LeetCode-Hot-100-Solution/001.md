##### 1 给定一个整数数组 nums 和一个整数目标值 target，请你在该数组中找出 和为目标值 的那 两个 整数，并返回它们的数组下标。你可以假设每种输入只会对应一个答案。但是，数组中同一个元素不能使用两遍。你可以按任意顺序返回答案。
***
###### 解法一：暴力求解
```c++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int n = nums.size();
        for(int i=0;i<n-1;++i){
            int t = target-nums[i];
            for(int j=i+1;j<n;++j){
                if(nums[j]==t)
                    return {i,j};
            }
        }
        return {};
    }
};
```

###### 解法二：使用字典
```C++
class Solution{
    public:
        vector<int> twoSum(vector<int>& nums,int target){
            unordered_map<int,int> hashtable;
            for(int i=0;i<nums.size();++i){
                auto it = hashtable.find(target-nums[i]);
                if(it != hashtable.end()){
                    return {it->second,i};
                }
                hashtable[nums[i]] = i;
            }
            return {};
        }
};
```
###### 待补充：unordered_map的使用方法
