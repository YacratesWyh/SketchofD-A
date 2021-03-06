#算法设计  

##蛮力法
不采用任何技巧，基于问题的描述直接地解决问题的方法  

	蛮力字符串匹配
	求两个整数的最大公因子
	查找元素
	百元买百鸡问题
 性能分析

	一般来说，蛮力法的效率相对较低
	蛮力法的思路很直接，实现简单，也容易被理解
	对于一些规模较小的问题，采用蛮力法是一种很经济的做法
	蛮力法的重要意义：作为求解问题的基本方案，用于衡量其它方法的正确性和效率

##分治法
把问题的一个实例分解成为属于同一问题的若干个较小规模的实例  
重复这个过程直到规模较小的实例很容易求解  
求解这些规模较小的实例  
合并较小问题的解，以得到原始问题的解  
	
	快速排序
	二叉树遍历
	大整数乘法
	矩阵乘法
效率估计:  
分治法并不总是能够改进时间复杂度  
好的情况可以将O(n^2)优化到O(nlog n)  


**减治法**    
减治法是把问题转化为规模较小的子问题，通过求解子问题来得到
原问题的解
对于有些问题，减治法与分治法存在一定的相关性

	减一个常量：选择排序
	减一个常因子：折半查找、二分法求解非线性方程
	减可变规模：辗转相除法

**与分治法的区别**  
分治法是将原问题分解成若干个同类型的小规模问题，但每个小规模问题都要处理，并且最后要合并  
减治法则每次都减小问题的规模，即使分解成若干个同类型的小规模问题，一般只需要处理其中的一个  

**变治法**  
把一个求解困难的问题转换成为一个有已知解法的问题，并且这种转换的复杂度不超过求解目标问题的算法复杂度

	对无序表的顺序查找=>对无序表排序+ 对有序表的二分查找  
	线性方程组的求解

##搜索算法  
基于状态空间树的回溯法和分支界限法为组合难题大规模实例的求解提供了可能性  
但回溯法和分支界限法都不能保证求解的效率  
**高效求解组合优化问题的核心依然是数学**   
###最优化问题  
最优化问题  

	目标函数
	约束条件
	可行解
	最优解

面向数值问题的最优化

	无约束规划，有约束规划
	线性规划，非线性规划，二次规划，凸规划，整数规划

可行解离散的优化问题：组合优化  

	八皇后问题
	旅行商问题
	背包问题

**回溯法**  

回溯法可以看作是对解空间状态树的**深度优先搜索**  

如果能够确定状态空间树上某个结点对应的部分解是没有希望的，则可以终止对其后续分支的搜索  

**分支界限法**  
估算解的下界  
利用解的下界帮助进行分支遍历的选择，是分支界限法的一种，称为最佳优先分支边界

##贪心算法-《数据结构与算法》5.5.4
	找零钱  
	背包问题
	编码问题
	找工作问题

通过一系列步骤来构造问题的解，每一步都是对当前已经存在的部分解的一个扩展，直至获得问题的完整解  
每个扩展步骤满足  

	可行性
	局部最优
	不可取消
**不是所有的优化问题都能用贪心算法求解**  
**如果一个优化问题，通过一系列的局部最优选择就可以得到问题的全局最优解，我们就说这个问题满足贪心选择性质**

	采用贪心算法求解优化问题时，可能存在多种贪心策略
	不同的贪心策略具有不同的性能
###满足贪心选择性质的例子  
	求最小生成树的Prim 算法
	求最小生成树的Kruskal 算法
	求单源最短路径的Dijkstra 算法
	Huffman 树和Huffman 编码
	最速下降法

##动态规划-《数据结构与算法》5.6.4
	阶段：把问题分成相互联系的有顺序的几个环节，称为阶段
	状态：某阶段的出发位置称为状态，即对该时刻进展情况的描述
	决策：从某阶段的一个状态演变到下一个阶段某状态的选择
**最优化原理:**对前面的决策所形成的状态而言，余下的部分决策必须构成最优策略  
**无后效性：**过去只通过当前状态影响未来，当前状态是历史的总结  

动态规划用空间换时间，在有大量重叠子问题的时候其优势才能充分体现出来  
典型的动态规划算法  

	求解图的全源最短距离的Floyd 算法
	解卷积码的Viterbi 算法

##随机算法
对某个特定输入的每次运行过程是随机的，运行结果也可能是随机的  
算法举例：  
<img src="./img/9-1.jpg" height=100>  

Sherwood 算法可以有效消除算法性能和输入数据实例之间的联系   
LAS VEGAS 算法在算法求解过程中引入随机性决策,往往能够加快求解过程，并且得到的解一定是正确的,可能会找不到解，或者找不到所有的解  
MONTE CARLO 算法是以概率为基础的统计模拟方法,并不保证得到的解一定是正确的

##算法优化
提高算法性能的思维方式具有鼓励性和经验性  
<img src="./img/9-2.jpg" height =200>  (From陈建生课件)  
算法的优化需要对算法的特性和要解决的问题有一定的了解，因此建议详细阅，这里只列出了提纲(so sorry)  
###输入增强技术
	KMP 算法
	Boyer-Moore 算法
	计数排序
###预构造技术
	二叉搜索树
	倒排索引
	并查集
	堆和堆排序

###时空平衡
牺牲空间换取时间or牺牲时间换取空间  
（一般来讲，由于存储的廉价和快速提高，前者的应用较多）  
散列依靠存储空间的冗余来解决冲突问题，进而实现更高的查找效率

###算法的组合
	快速排序的改进
	非线性方程迭代的保护法

##计算复杂性
**算法性能分析**
算法稳定性：排序稳定性、数值稳定性等
时间复杂度与渐进表示O(n^2)
空间复杂度：占用存储空间的大小
处理器复杂度：占用处理器的多少

###图灵机
	多道图灵机与标准图灵机的计算能力相同
	多带图灵机与标准图灵机的计算能力相同
	多道多带图灵机与标准图灵机的计算能力相同

	只有两个状态的图灵机与标准图灵机的计算能力相同
	只有两个符号的图灵机与标准图灵机的计算能力相同
###P与NP问题  
**P/NP 问题**  
复杂度类P即为所有可以由一个确定型图灵机在多项式表达的时间内解决的问题；类NP由所有可以在多项式时间内验证解是否正确的决定问题组成(From wikipedia)  
<img src="./img/9-3.jpg" height =300>

#考试
	注重概念的理解
	注重算法的解题思路
	注重知识的掌握和灵活运用
	不考名词解释
From(白铂)

	试题种类：填空题、简答题、问答题
	试题覆盖：以课堂讲授为准
	非数值：数值：算法 5:3:2
From(陈建生)

---
以上  
By [jas0n1ee](mailto:i@jas0n1ee.me)  
全文[源文件](https://github.com/jas0n1ee/SketchofD-A)托管在Github中