## 用 lambda 实现迭代效果

### 困难

    没有函数名，则无法引用自己，从而无法实现迭代

### 解决

    借助另一个lambda函数，使自己本身成为其参数，又二者的参数保持同一，那么就做到了引用自己的目的

### 示例

```python

from operator import sub, mul

def make_anonymous_factorial():

    return (lambda f: lambda k: f(f, k))(lambda f, k: k if k == 1 else mul(k, f(f, sub(k, 1))))

```

这样一个求阶乘的函数，仅仅只有一句 return，就是上面的应用
