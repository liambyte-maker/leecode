# 704 二分查找

方法一：左闭右闭
```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        left,right=0,len(nums)-1
        
        while left<=right:
            middle=left+(right-left)//2
            if nums[middle]>target:
                right=middle-1
            elif nums[middle]<target:
                left=middle+1
            else:
                return middle
        return -1
```
方法二：左闭右开
```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        left,right=0,len(nums)      #区别， 右边变成开区间，所以不存在left=right
        while left<right:
            middle=left+(right-left)//2
            if nums[middle]>target:
                right=middle        #区别  right=middle 而不是middle-1,因为开区间
            elif nums[middle]<target:
                left=middle+1
            else:
                return middle
        return -1


        
        
        
        
        

```




