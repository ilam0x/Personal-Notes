# 1 Two Sum

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
       
        for i in range(len(nums)):
            a = target - nums[i]
            if a in nums[i+1:]: 
                result = [i, nums.index(a,i+1)] #从下标i+1
                return result
        
```

# 2. Add Two Numbers

> 将列表中的数字合并成一个数字 input [1,2,3] output 123
>
> ```python
> #method 1
> list = int(''.join([str(i) for i in list])
> 
> ```
>
> 

```python
        def join_list(li):
            temp = [str(i) for i in li]
            l = int(''.join(temp))
        n1 = join_list(l1)
        n2 = join_list(l2)
        
        sum = str(n1+n2)
        l3 = [int(a) for a in sum]
        
        
        return l3
```

