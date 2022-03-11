# **Python作业**

## 运行环境

- VS Code 1.59.1
- Python 3.10.2



## 代码托管

Github: 



## 作业

### Lab00

#### 1. What Would Python Do? (WWPD) 

实验和作业的一部分练习是预测Python解释器的行为（WWPD， Python会怎么做）。具体细节参考lab00准备开始.md。此处仅放置截图信息。

![scrshot_wwpd.png](https://s2.loli.net/2022/03/11/slATZtfxQaO9WwY.png)



#### 2. Parson 问题

实验和作业的一部分练习是Parson问题。Parson问题由一组部分完整的代码行组成。此次问题的任务是返回“I love CS 61A!”字符串。

```python
def ilove61a():
    """
    Write a function that returns the string "I love CS 61A!".
    >>> ilove61a() # .Case 1
    'I love CS 61A!'
    """
    "*** YOUR CODE HERE ***"
    return "I love CS 61A!"
```



#### 3. 编程问题

lab00.py，要求返回值“2020”。

```python
def twenty_twenty_two():
    """Come up with the most creative expression that evaluates to 2022,
    using only numbers and the +, *, and - operators.

    >>> twenty_twenty_two()
    2022
    """
    return int(1000*20/10+30-8)
```



## 问题2：k in Num

要求：编写函数 `k_in_num`，接受两个整数 `k` 和 `num`：

> 如果 `num` 有数位(digit)  `k` ，返回 `True`
>
> 如果 `num` 没有数位(digit) `k` ，返回 `False`
>
> 如果没有数位, 返回 `0`

实现方法很简单，只需将k和num转成字符串类型，再用in判断num中是否有字符k即可。

```python
def k_in_num(k, num):
    """
    Complete k_in_num, a function which returns True if num has the digit k and
    returns False if num does not have the digit k. 0 is considered to have no
    digits.

    >>> k_in_num(3, 123) # .Case 1
    True
    >>> k_in_num(2, 123) # .Case 2
    True
    >>> k_in_num(5, 123) # .Case 3
    False
    >>> k_in_num(0, 0) # .Case 4
    False
    """
    "*** YOUR CODE HERE ***"
    s_num=str(num)
    s_k=str(k)
    if(s_k in s_num):
        return True
    else: 
        return False
```



## 问题3： A Plus Abs B

Python 的 `operator` 模块定义了Python内在的二元算术运算符。例如，调用 `operator.add(2, 3)` 等价于调用表达式 `2 + 3` ，都会返回 `5` 。 

在下面的函数中填空，使得 `a` 加上 `b` 的绝对值，并且不调用 `abs` 。只修改代码中的空格处。

此处需要使用匿名函数`lambda`，并赋予f该函数，即f代表对应的函数，仅需向f传递参数即可。

```python
def a_plus_abs_b(a, b):
    """Return a+abs(b), but without calling abs.

    >>> a_plus_abs_b(2, 3)
    5
    >>> a_plus_abs_b(2, -3)
    5
    >>> a_plus_abs_b(-1, 4)
    3
    >>> a_plus_abs_b(-1, -4)
    3
    """
    if b < 0:
        f = lambda x,y:x-y
    else:
        f = lambda x,y:x+y
    return f(a, b)
```



## 问题4： Two of Three

 编写函数，接受三个正数作为参数，并返回两个较小数字平方的和。**在函数体中只是用一行代码实现**。

只需要用三个参数的平方和减去最小数（用min函数）的平方和即可。

```python
def two_of_three(i, j, k):
    """Return m*m + n*n, where m and n are the two smallest members of the
    positive numbers i, j, and k.

    >>> two_of_three(1, 2, 3)
    5
    >>> two_of_three(5, 3, 1)
    10
    >>> two_of_three(10, 2, 8)
    68
    >>> two_of_three(5, 5, 5)
    50
    """
    return i*i+j*j+k*k-max(i,j,k)*max(i,j,k)
```



## 问题5：最大因子

编写函数接受一个**大于1**的整数 `n` 并返回不是 `n` 本身的最大因子。 

令f = n - 1，判断n对f求余是否等于0.每次迭代f自减1直到f = 1.

```python
def largest_factor(n):
    """Return the largest factor of n that is smaller than n.

    >>> largest_factor(15) # factors are 1, 3, 5
    5
    >>> largest_factor(80) # factors are 1, 2, 4, 5, 8, 10, 16, 20, 40
    40
    >>> largest_factor(13) # factor is 1 since 13 is prime
    1
    """
    "*** YOUR CODE HERE ***"
    f=n-1
    while(n%f!=0):
        f-=1
    return f
```

