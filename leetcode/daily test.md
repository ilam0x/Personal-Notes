# Complex Number Multiplication

```python
class Solution:
    def complexNumberMultiply(self, num1: str, num2: str) -> str:
        add1 = num1.index("+")
        add2 = num2.index("+")
        
        x1,y1 =int(num1[:add1]),int(num1[add1+1:-1])
        x2,y2 =int(num2[:add2]),int(num2[add2+1:-1]) //变量名修改
        
#        (x1-y1i)*(x2-y2i)= x1x2-(x1y2+-x2y1)i-y1y2
        
        mul = str(x1*x2-y1*y2)+"+"+str(x1*y2+x2*y1)+"i"
#        return x1,x2,y1,y2
        return mul
        
```

# Sum of Square Numbers

Given a non-negative integer `c`, decide whether there're two integers `a` and `b` such that `a2 + b2 = c`.

```python
import math
class Solution:
    def judgeSquareSum(self, c: int) -> bool:
        
        left = 0
        right = int(math.sqrt(c))

        while left <= right:
            sqrt_sum = left**2 + right **2
            if (sqrt_sum == c):
                return True
            else:
                if (sqrt_sum < c):
                    left +=1
                else:
                    right-=1
        return False
            

```

