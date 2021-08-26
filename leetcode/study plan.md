# 二分法

## 35 Search Binary Insert

特征：顺序排列，或折叠[4,5,6,1,2,3]

> 1. left = 0, right = length-1, 
>    mid = left +(right-left)/2 //防止直接left+right超过整数类型的最大值
> 2. 向下取整`math.floor(mid)`
> 3. 当left <= right，
>    1. mid = target, return mid;
>    2. mid < target, left = mid+1 // left指针移到mid右一位
>    3. mid > target, right = mid-1

``` js
//二分法
var searchInsert = function(nums, target) {
    let left=0, right = nums.length-1;
    while (left <= right){
    let mid = Math.floor(left + (right - left)/2);
        if (nums[mid] === target){
            return mid;
        } else if (nums[mid] > target){
            right = mid-1;
        } else {
            left = mid+1;
        }}
    return right+1;
    };
```



## 278. First Bad Version

```js
var solution = function(isBadVersion) {
    /**
     * @param {integer} n Total versions
     * @return {integer} The first bad version
     */
     return function(n) {
      let left = 1, right = n;
      while (left < right) { //不能=，死循环
        let mid = Math.floor( left +  (right - left) / 2 );
        if (isBadVersion(mid)) {
            right = mid;
        } else {
            left = mid + 1; //顺序列表，如果不是中位数则前面都不是
        }}
      return left;
    };
};

```





## 704　二分搜索 binary search

```js
var search = function (nums,target){
    let left = 0, right = nums.length -1;
    while(left <= right){
        mid = Math.floor(left+ (right-left)/2); //%Math大写
        if(nums[mid] === target){
            return mid;
        } else if (target < nums[mid]) {
            right = mid - 1;
        } else {
            left = mid + 1;
        }
    }
    return -1;
}
```



# 双指针

## 189. Rotate Array

```python
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        for i in range(k):
            nums.insert(0,nums[-1])
            #nums.remove(a[-1]) 是删除第一个匹配列表最后一位的值
            nums.pop() #删除最后一个值
        --------------------------------
        for i in range(k):
            nums.insert(0,nums.pop()) 
        #3129ms
       ----------------------------
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        n=[]
        first = nums[-k:]
        second = nums[-len(nums):-k] //
        n = first + second
        for i in range(len(nums)): //复制已有列表
            nums[i]=n[i]
    
```



## 977. Squares of a Sorted Array

```python
class Solution:
    def sortedSquares(self, nums: List[int]) -> List[int]:
        left, right = 0, len(nums)-1
        new =[]
        while left <= right:
            if abs(nums[left]) < abs(nums[right]):
              new.insert(0,nums[right]**2)
              right-=1           
            else:
              new.insert(0,nums[left]**2)
              left+=1

        return new
        
```



## 283. Move Zeroes

```python
#slow
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        right = len(nums)
        if 0 in nums:
            for i in range(right):
                nums.remove(0)
                nums.append(0)
                right -= 1
```

## 167.Two Sum II - Input array is sorted

没用双指针的方法

![image-20210826015620514](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210826015620514.png)

```python
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        for a in range(len(numbers)):
            b = target-numbers[a]
            if b in numbers[a+1:]:
                return [a+1,numbers.index(b,a+1)+1]

```

双指针

```python
left = 0
right = len(numbers)-1
while (left < right):
    sum = numbers[left]+numbers[right]
    if (sum == target):
        retun [left+1,right+1]
    elif (sum < target):
        left+=1
    elif:
        right-=1
```

