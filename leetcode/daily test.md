Complex Number Multiplication

```python
class Solution:
    def complexNumberMultiply(self, num1: str, num2: str) -> str:
        add1 = num1.index("+")
        add2 = num2.index("+")
        
        x1,y1 =int(num1[:add1]),int(num1[add1+1:-1])
        x2,y2 =int(num2[:add2]),int(num2[add2+1:-1]) //复制粘贴后没有改完参数
        
#        (x1-y1i)*(x2-y2i)= x1x2-(x1y2+-x2y1)i-y1y2 //题目看成sum
        
#        mul = str(x1*x2-y1*y2)+"+"+str(x1*y2+x2*y1)+"i"
        return x1,x2,y1,y2
#        return mul
        
```

