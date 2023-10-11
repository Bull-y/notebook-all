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
1. 导入numpy库并简写为np
   ```python
   import numpy as np
   ``` 
2. 打印numpy的版本和配置说明
   ```python
   print(np.__version__)
   print(np.show_config())
   ```
3. 创建一个长度为10的空向量
   ```python
   print(np.zeros(10))
   ```
4. 如何找到任何一个数组的内存大小?
   ```python
   z=np.zeros((10,10))
   print("%d bytes"%(z.size*z.itemsize))  # 100*8
   ```
5. 如何从命令行得到numpy中add函数的说明文档?
   ```python
   print(np.info(numpy.add))
   ```
6. 创建一个长度为10并且除了第五个值为1的空向量
   ```python
   data = np.zeros(10)
   data[4]=1
   print(data)
   ```
7. 创建一个值域范围从10到49的向量
   ```python
   data = np.arange(10, 50)  # 左闭右开
   print(data)
   ```
8. 反转一个向量(第一个元素变为最后一个)
   ```python
   data = np.arange(10, 50)
   data=data[::-1]  # 步长为-1
   print(data)
   ```
9.  创建一个 3x3 并且值从0到8的矩阵
    ```python
    a = np.arange(9).reshape(3, 3)
    print(a)
    ```
10. 找到数组[1,2,0,0,4,0]中非0元素的位置索引
    ```python
    nz = np.nonzero([1, 2, 0, 0, 4, 0])
    print(nz)
    ```
11. 创建一个 3x3 的单位矩阵
    ```python
    data = np.eye(3)
    print(data)
    ```
12. 创建一个 3x3x3的随机数组
    ```python
    data = np.random.random((3, 3, 3))
    print(data)
    ```
13. 创建一个 10x10 的随机数组并找到它的最大值和最小值
    ```python
    data = np.random.random((10, 10))
    max1,min1 = data.max(),data.min()
    print(data)
    print(max1)
    print(min1)
    ```
14. 创建一个长度为30的随机向量并找到它的平均
    ```python
    data = np.random.random(30)
    datamean = data.mean()
    print(datamean)
    ```
15. 创建一个二维数组，其中边界值为1，其余值为0
    ```python
    data = np.ones((10,10))
    data[1:-1,1:-1]=0
    print(data)
    ```
16. 对于一个存在数组，如何添加一个用0填充的边界？
    ```python
    data = np.ones((5,5))
    data =np.pad(data,pad_width=1,mode='constant',constant_values=0)
    print(data)
    ```
17. 以下表达式运行的结果分别是什么?
    ```py
    print(0 * np.nan)  # N
    print(np.nan == np.nan)  # F
    print(np.inf > np.nan)  # F
    print(np.nan - np.nan)  # N
    print(0.3 == 3 * 0.1)  # F
    ```
18. 创建一个 5x5的矩阵，并设置值1,2,3,4落在其对角线下方位置
    ```py
    data = np.diag(1 + np.arange(4), k=-1)
    print(data)
    ```
19. 创建一个8x8 的矩阵，并且设置成棋盘样式
    ```python
    data = np.zeros((8,8),dtype=int)
    data[1::2,::2]=1
    data[::2,1::2]=1
    print(data)
    ```
20. 考虑一个(6,7,8) 形状的数组，其第100个元素的索引(x,y,z)是什么?
    ```py
     print(np.unravel_index(100, (6, 7, 8)))
    # 没看懂
    ```
21. 用tile函数去创建一个 8x8的棋盘样式矩阵
    ```py
    data = np.tile(np.array([[0, 1], [1, 0]]), (4, 4))
    print(data)
    ```
22. 对一个5x5的随机矩阵做归一化
    ```py
    data = np.random.random((5, 5))
    datamax, datamin = data.max(), data.min()
    data = (data - datamin) / (datamax - datamin)
    print(data)
    ```
23. 创建一个将颜色描述为(RGBA)四个无符号字节的自定义dtype?
    ```py
     bu yong kan
    ```
24. 一个5x3的矩阵与一个3x2的矩阵相乘，实矩阵乘积是什么?
    ```py
    data = np.dot(np.ones((5, 3)), np.ones((3, 2)))
    print(data)
    ```
25. 给定一个一维数组，对其在3到8之间的所有元素取反
    ```py
    data = np.arange(10)
    data[(data > 3) & (data < 8)] *= -1
    print(data)
    ```
26. 下面运行结果是什么？
    ```py
    print(sum(range(5), -1))  # 9

    from numpy import *

    print(sum(range(5), -1))  # 10
    ```
27. 考虑一个整数向量z,下列表达合法的是哪个?
    ```py
     ...
    ```
28. ...
29. 如何从零位对浮点数组做舍入?
    ```py
    data1 = np.random.uniform(-10,+10,10)
    print(np.copysign(np.ceil(np.abs(data1)),data1))
   # 没看懂
    ```
30. 找到两个数组中的共同元素？
    ```py
    import numpy as np

    data1 = np.random.randint(0, 10, 10)
    data2 = np.random.randint(0, 10, 10)

    print(np.intersect1d(data1, data2))
    ```
31. 如何忽略所有的numpy的警告
    ```py
     ...
    ```
32. ...
33. ...
34. ...
35. 如何计算(A+B)*(-A/2)(不建立副本)
    ```py
    A=np.ones(3)*1
    B=np.ones(3)*2

    print(np.add(A, B, out=B))
    print(np.divide(A, 2, out=A))
    ```
36. 用五种不同的方法去提取一个随机数组的整数部分
   ```py
    data1 = np.random.uniform(0,10,10)
    print(data1-data1%1)
    #-----------------------------------------------
    print(np.floor(data1))
    #-----------------------------------------------
    print(np.ceil(data1)-1)
   #-----------------------------------------------
    print(data1.astype(int))
    #-----------------------------------------------
    print(np.trunc(data1))
   ```
37. 创建一个5x5的矩阵，其中每行的数值范围从0到4
    ```py
    data = np.zeros((5,5))
    data+=np.arange(5)
    print(data)
    ```
38. 通过考虑一个可生成10个整数的函数，来构建一个数组
    ```py
    import numpy as np


    def genter():
       for x in range(10):
          yield x


    data = np.fromiter(genter(),dtype=float,count=-1)
    print(data)


    ```
39. 创建一个长度为10的随机向量，其值域范围从0到1，但是不包括0和1
    ```py
    data = np.linspace(0,1,11,endpoint=False)[1:]
    print(data)

    ```
40. 创建一个长度为10的随机向量，并将其排序
    ```py
    data = np.random.random(10)
    data.sort()
    print(data)
    ```
41. 对于一个小数组，如何用比 np.sum 更快的方式对其求和?
    ```py
    data = np.arange(10)
    # print(np.sum(data))
    print(np.add.reduce(data))
    ```
42. 对于两个随机数组A和B，检查它们是否相等
    ```py
    A = np.random.randint(0, 2, 5)
    B = np.random.randint(0, 2, 5)
    equal = np.allclose(A, B)
    data1 = np.array_equal(A,B)
    print(data1)
    print(equal)
    ```
43. 创建一个只读数组(read-only)
    ```py
    data = np.zeros(10)
    data.flags.writeable = False
    data[0] = 1
     ```
44. 将笛卡尔坐标下的一个10x2的矩阵转换为极坐标形式
   ```python
   data = np.random.random((10, 2))
   X, Y = data[:, 0], data[:, 1]
   R = np.sqrt(X ** 2 + Y ** 2)
   T = np.arctan2(Y, X)
   print(R)
   print(T)
   ```
45. 创建一个长度为10的向量，并将向量中最大值替换为1
   ```py
   data = np.random.random(10)
   data[data.argmax()]= 1
   print(data)
   ```
46. 创建一个结构化数组，并实现 x 和 y 坐标覆盖[0,1]x[0,1] 区域
   ```py
   ...
   ```
47. 给定两个数组X和X，构造柯西矩阵C (Cij= 1/(xi-yj))
   ```py
   X=np.arange(8)
   Y=X+0.5
   C=1.0/np.subtract.outer(X,Y)
   print(np.linalg.det(C))
   ```

总结：numpy用到的语法：
1. **np.zeros**
   - 默认为：float64
   - 一维数组：a=np.zeros(5)
   - 二维数组：b=np.zeros((5,5))
   - 三维数组：c=np.zeros((5,2,2))
   - 整型一维数组：d=np.zeros(3,int)
   - 使用dtype转换数据类型：
     - e=np.zeros(3)
     - e.dtype=int(int32)
2. **z.size**表示有多少元素，**z.itemsize**表示一个元素占多少字节
3. **np.arange**
   - 整型
   - 表示一维数组
   - 起，尾，步长
   - a=np.arange(6)
   - a=np.arange(6,10)
   - c=np.arange(6,20,2)
4. **np.array**
   - 默认为: int32
   - numpy.array(object, dtype=None)
   - a = np.array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
   - b = np.array([[1, 2], [3, 4]])
   - c = np.array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9], dtype=np.float32)
5. **np.nonzero**
   - 返回的是目标数组a中非零元素的索引
   - a = np.nonzero([1, 0, 2, 0, 3, 0])
   - b = np.nonzero([[1, 1, 0],[0, 0, 0],[1, 0, 3]])
6. **np.eye**
   - 浮点数
   - numpy.eye(N,M=None,k=0,dtype=< class 'float' >,order='C)
   - a = np.eye(3)
   - b = np.eye(4, k=1)
   - c = np.eye(4, k=2)
   - d = np.eye(4, k=-1)
   - e = np.eye(4, k=-2)
   - a = np.eye(3)[[1,2,0,1,2,1,2,1,2]]
   - a = np.eye(3,k=-1)[[1,2,0,1,2,1,2,1,2]]
7. **np.reshape**
   - 对数组的结构进行改变。
   - 函数中的参数需要满足乘积等于数组中数据总数。
   - reshape()函数得出的数组与原数组使用的是同一个存储空间，改变一个，另一个也随之改变。
   - shape和reshape()函数都是对于数组(array)进行操作的，对于list结构是不可以的
   - print(np.array([1, 2, 3, 4, 5, 6, 7, 8]).reshape(2, 4))
   - print(np.array([1, 2, 3, 4, 5, 6, 7, 8,9]).reshape(-1, 3))
   - picture_data = data.reshape(-1,8,8,1)
8. **np.shape**
   - 了解数组的结构
   - print(np.array([1, 2, 3, 4, 5, 6, 7, 8]).shape)
   - print(np.array([[1, 2], [2, 3], [3, 4]]).shape)
   - print(np.array([1, 2, 3, 4, 5, 6, 7, 8]).shape[0])
   - print(np.array([[1, 2], [2, 3], [3, 4]]).shape[1])
9. **np.random.random**
   - 浮点数,从0-1中随机的均匀分布
   - 一维：print(np.random.random(3))
   - 二维：print(np.random.random((3, 4)))
   - 三维：print(np.random.random((3, 4， 5)))
10. **np.random.rand**
    - 和np.random.random没有任何区别
11. **np.random.randn**
    - 浮点数
    - 服从均值为0，方差为1的标准正态分布，也可以为负值
    - print(np.random.randn())
      - 参数不指定，生成的是一个浮点型的数
    - print(np.random.randn(2))
      - 指定一个数字，生成一维数组
    - print(np.random.randn(2,2))
      - 指定两个数字，生成二维数组
12. **np.random.randint(low，high，size，dtype)**
       - 整型
       - print(np.random.randint(1))
         - 0
       - print(np.random.randint(2))
         - 随机生成1或0的数字
       - print(np.random.randint(1,5))
         - 随机生成1-4的数字
       - print(np.random.randint(1,5,2))
         - 1行2列的范围1-4的数组
       - print(np.random.randint(1,5,(2,2)))
         - 2行2列的范围1-4的数组
       - print(np.random.randint(low=2, high=10, size=(3, 3), dtype=np.uint8))
         - uint8类型的3行3列范围2-9的数组
13. **np.random.uniform(low，high，size)**
      - 浮点型
      - 无dtype
      - 生成服从指定范围内的均匀分布的元素
      - print(np.random.uniform())
        - 参数不指定，生成的是一个0-1浮点型的数
      - print(np.random.uniform(1))
        - 1.0
      - print(np.random.uniform(2))
        - 1-2的浮点数
      - print(np.random.uniform(5, 10))
        - 5-9的浮点数
      - print(np.random.uniform(5, 10,(3,3)))
        - 3行3列的范围5-9的数组
14. **np.full(shape, fill_value, dtype=None, order=‘C’)**
      - 构造一个长度为 shape fill_value数组。
      - print(np.full((2, 3), 7.1))
        - 2行3列的均为7.1的数组
15. **numpy.zeros(shape, dtype=float, order='C')**
      - 构造一个长度为 shape 浮点型0数组。
      - print(np.zeros(3))
        - 生成1行3列的0数组
      - print(np.zeros((3,2)))
        - 生成3行2列的0数组
16. **empty(shape, dtype=float, order='C')**
      - 构造一个长度为 shape 的未初始化数组，这个数组的元素可能是内存位置上存在的任何数值。
      - print(np.empty(3))
      - print(np.empty((3,2)))
      - print(np.empty(shape=(2, 3), dtype=int))
17. **numpy.ones(shape, dtype=None, order='C')**
      - 构造一个长度为 shape 浮点型1数组。
      - print(np.ones(3))
        - 生成1行3列的1数组
      - print(np.ones((3,2)))
        - 生成3行2列的1数组
18. **np.tile(A, reps)**
      - 以数组为单位进行扩展
      - print(np.tile(np.arange(0, 40, 10), (3, 5)))
19. **np.r_[A ,B ,C]**
      - 拼接技术
      - print(np.r_[[1, 2, 3], [4, 5, 6], [7, 8, 9]])
20. **numpy.linspace(start, stop, num=50, endpoint=True, retstep=False, dtype=None)**
      - 间隔采样，在指定的间隔内返回均匀间隔的数字
      - print(np.linspace(-5, 5))
        - 生成-5-5的间隔内返回均匀间隔的50个数字
      - print(np.linspace(-5, 5, 5, False))
        - 生成不包括5的间隔内返回均匀间隔的5个数字
      - print(np.linspace(start=-5, stop=5, num=5, endpoint=True, retstep=True))
        - 生成不包括5的间隔内返回均匀间隔的5个数字，后面加步长
      - print(np.linspace(start=-5, stop=5, num=5, endpoint=True, retstep=True, dtype=int))
        - 生成不包括5的间隔内返回均匀间隔的5个int数字，后面加步长
      - (array([-5. , -2.5,  0. ,  2.5,  5. ]), 2.5)
      - (array([-5, -3,  0,  2,  5]), 2.5)
21. **numpy.mean(a, axis=None, dtype=None, out=None, keepdims)**
      - print(np.mean(np.array([[1, 2], [3, 4]])))
        - 返回所有元素的平均值
      - print(np.mean(np.array([[1, 2], [3, 4]]),axis=1))
        - 返回1行2列的对各行求的均值
      - print(np.mean(np.array([[1, 2], [3, 4]]),axis=0))
        - 返回1行2列的对各列求的均值
      - print(np.mean(np.array([[1, 2], [3, 4]]),axis=1,dtype = np.float32))
        - 返回1行2列的对各列求的float32型均值
22. **np.amax(a, axis=None, out=None, keepdims=< no value >, initial=< no value >, where=< no value >)**
      - 与np.max相同
      - axis=0 代表列 , axis=1 代表行 ， axis= None 代表所有展宽取最大
23. **amin(a, axis=None, out=None, keepdims=< no value >, initial=< no value >, where=< no value >)**
      - 与np.min相同
      - axis=0 代表列 , axis=1 代表行 ， axis= None 代表所有展宽取最大
24. **np.diag(v, k)**
      - 返回二维数组v中k相关的对角线数据组成的一维数组
      - 返回一个构造的二维与k相关的类对角线形二维数组
      - 一维数组k缺省：print(np.diag(np.arange(1, 6)))
        - 5,5
      - 一维数组k+1：print(np.diag(np.arange(1, 6),k=1))
        - 6,6
      - 一维数组k-1：print(np.diag(np.arange(1, 6),k=-1))
        - 6,6
      - 二维数组k缺省：print(np.diag(np.array([[0, 1, 2], [3, 4, 5], [6, 7, 8]])))
        - 1,3
      - 二维数组k+1：print(np.diag(np.array([[0, 1, 2], [3, 4, 5], [6, 7, 8]]), k=1))
        - 1,2
      - 二维数组k-1：print(np.diag(np.array([[0, 1, 2], [3, 4, 5], [6, 7, 8]]), k=-1))
        - 1,2
25. `np.pad(array, pad_width, mode, **kwargs)`
    - 为了避免因为卷积运算导致输出图像缩小和图像边缘信息丢失，常常采用图像边缘填充技术
    - 一维数组：print(np.pad(np.arange(1, 6), (2, 3), 'constant', constant_values=(4, 6)))
      - 左右添加
    - 二维数组：print(np.pad((np.arange(95, 99).reshape(2, 2)), ((3, 2), (2, 3)), 'constant', constant_values=(1, 2)))
      - 行和列都添加相同的值
    - 二维数组：print(np.pad((np.arange(95, 99).reshape(2,2)), ((3, 2), (2, 3)), 'constant', constant_values=((0, 0), (1, 2))))
      - 行和列添加不同的值
    - 二维数组：print(np.pad((np.arange(95, 99).reshape(2,2)), ((3, 2), (2, 3)), 'constant'))
      - 行和列添加0
26. **np.floor**
    - print(np.floor([-2.5, -1.7, -1.5, -0.2, 0.2, 1.5, 1.7, 2.0]))
    - 向下取整
27. **np.ceil**
    - print(np.ceil([-2.5, -1.7, -1.5, -0.2, 0.2, 1.5, 1.7, 2.0]))
    - 向上取整
28. **numpy.allclose(a, b, rtol=1.e-5, atol=1.e-8, equal_nan=False)**
    - absolute(a - b) <= (atol + rtol * absolute(b))返回True
    - print(np.allclose([0.12, 0.17, 0.24, 0.29], [0.13, 0.19, 0.26, 0.31], 0.1))
      - False
    - print(np.allclose([0.12, 0.17, 0.24, 0.29], [0.13, 0.18, 0.26, 0.31], 0.1))
      - True
29. **numpy.isclose(a, b, rtol=1.e-5, atol=1.e-8, equal_nan=False)**
    - absolute(a - b) <= (atol + rtol * absolute(b))返回True
    - 比较每一个值
30. **np.array_equal**
    - 检查两个数组是否具有相同的形状和元素,还可用在数组和列表之间、列表与列表间的比较
    - np.array_equal(A,B)
      - 必须形状一样
      - 必须参数一样
      - 才True
31. **np.unique**
    - 该方法排序后，会对数组重新进行降重排序
    - print(np.unique(np.array([6, 5, 7, 3, 6, 3, 4, 3, 9, 3, 0, 6]))) 
      - [0 3 4 5 6 7 9]
    - print(np.unique(np.array([[3, 2, 3, 6], [3, 0, 3, 8], [3, 2, 3, 6]])))
      - 1,1
    - print(np.unique(np.array([[3, 2, 3, 6], [3, 0, 3, 8], [3, 2, 3, 6]]),axis=0))
      - 对列降重
    - print(np.unique(np.array([[3, 2, 3, 6], [3, 0, 3, 8], [3, 2, 3, 6]]),axis=1))
      - 对行降重
