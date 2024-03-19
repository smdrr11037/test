# Leftist Heaps
-------
review: 堆的操作

* 插入

* 删除

* 合并——复杂度相当于重新建堆
<!-- 具体的说明 -->
-------
左偏堆——利用结构的不平衡，加速堆的合并

### Definition
* 有两个儿子的节点是内部节点，其余为外部节点

* **null path length, Npl(x)**: 到外部节点的最短路径

* 定义Npl(null) = -1

* **左偏树**即所有的节点，左儿子的Npl大于等于右儿子的Npl
<!-- 图片例子 -->
> Theorem: 右路径为r的左偏树，至少有$2^r-1$个节点
<!-- ? -->
<!-- 数学归纳法 -->
> r = 1时

> r = k时，假设成立

> r =  k+1时，右子树的Npl为k+1
>
> tips:
>
> 左子树的右路径为k，因此左子树至少有$2^r-1$个节点


### 实现：
```c
struct TreeNode
{
    ElementType     Element;
    PriorityQueue   Left;
    PriorityQueue   Right;
    int             Npl;
};
```

方法一：递归

1. Merge(R)

2. Attach()

3. Swap

<!-- 图片 -->

<!-- 代码 -->


方法二：迭代                              

delete min

# Skew Heaps
------
左偏树合并时不判断npl，直接交换左右子树，就是斜堆

<!-- 怎么插入 -->

<!-- 例子 -->


------
均摊分析（势能法）
<!-- ? -->

* 势能函数$\Phi(D_i)$=重节点的个数

* 重节点：右子树节点个数严格大于左子树

* 只有右路径节点的轻重会改变

* 操作后，重节点一定变轻，轻节点不一定变重，为求上界，假设轻节点都变重

<!-- 推导和计算 -->