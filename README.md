# week_14
# 非比较排序
不是元素之间不能比较，而是不再比较大小（java中不再使用compareTo），主要应用于字符串排序。
## 计数排序
leetcode 75颜色分类，相当于给定数组只包含0，1，2对数组排序。
在之前学习中使用的三路快排，使用O(n)的复杂度实现了原地的排序分类。
使用计数排序
```c++
class  Solution {
public:
	void  sortColors(vector<int>&  nums) {
		int  cnt[3]={};
		for(int num:nums)
			cnt[num]++;
		for(int i=0;i<cnt[0];i++)
			nums[i]=0;
		for(int i=cnt[0];i<cnt[0]+cnt[1];i++)
			nums[i]=1;
		for(int i=cnt[0]+cnt[1];i<cnt[0]+cnt[1]+cnt[2];i++)
			nums[i]=2;
	}
};
```
这种方法有一定的局限性，当种类较多时这种代码就不适用，需要进行一定修改。
