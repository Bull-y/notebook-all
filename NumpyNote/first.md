## 基础numpy语法
1. 为什么使用numpy?
   - **代码更加简洁：** Numpy直接以数组、矩阵为粒度计算并且支持大量的数学函数，而Python需要用for循环从底层实现;
   - **性能更高效:** Numpy的数组存储效率和输入输出计算性能，比Python使用List或者嵌套List好很多;
     - Numpy的数据存储和Python原生的List不一样
     - Numpy的大部分代码是C实现的，故高效
2. 生成array:
   ```python
    import numpy as np

    a = np.zeros((2, 3))  # 两行三列，每个数据是0
    print(a)
    b = np.full((2, 3), 1)
    print(b)
   ```
3. 列表转数组：
   ```python
    import numpy as np

    list1 = [[1, 2],
            [3, 4],
            [5, 6]]

    c = np.array(list1)

    print(c)
   ```
3. 取数组元素：
   ```python
    import numpy as np

    list1 = [[1, 2],
            [3, 4],
            [5, 6]]

    array1 = np.array(list1)
    d = array1[1, 0]
    d1 = array1[:, 0]  # 冒号是所有的意思
    d2 = array1[2, :]
    print(d)   # 3
    print(d1)  # [1 3 5] 
    print(d2)  # [5 6]  
   ```
4. 点乘：
   ```python
    import numpy as np

    array1 = np.array([1, 2, 3])
    array2 = np.array([3, 4, 5])

    y = np.dot(array1, array2)
    print(y)  # 26  
    --------------
    import numpy as np

    array1 = np.array([[1, 2, 3],
                    [4, 5, 6]])
    array2 = np.array([[1, 4],
                    [2, 5],
                    [3, 6]])

    y = np.dot(array1, array2)
    print(y)
   ```
   两层神经网络之间有权重，权重是矩阵，输入是向量。w^Tx
5. 花乘与相加：
   ```python
    import numpy as np

    array1 = np.array([[1, 2, 3],
                    [4, 5, 6]])
    array2 = np.array([[1, 2, 3],
                    [4, 5, 6]])

    y1 = array1*array2
    y2 = array1+array2
    print(y1)
    print(y2)
   ```
6. 取平均
    ```python
    import numpy as np

    a = np.array([[1, 2],
                [3, 4],
                [5, 6]])
    b=np.mean(a,axis=0)  # 纵轴
    b=np.mean(a,axis=1)  # 横轴
    b=np.mean(a)  # 所有
    print(b)
    ```
7. 求最大值
   ```python
   import numpy as np

    a = np.array([[-1, 2],
                [-3, 4],
                [-5, 6]])
    b = np.maximum(0, a)
    print(b)
    --------------------
    import numpy as np

    a = np.array([[-1, 2],
                [-3, 4],
                [-5, 6]])
    c = np.array([[0, 2],
                [-3, 1],
                [-5, 0]])

    b = np.maximum(a, c)
    print(b)
    --------------------
    import numpy as np

    a = np.array([[-1, 2],
                [-3, 4],
                [-5, 6]])
    b1 = np.max(a,axis = 1)
    b2 = np.max(a,axis = 0)
    b3 = np.max(a)
    print(b1)
    print(b2)
    print(b3)
   ```
## numpy100道题
1. 