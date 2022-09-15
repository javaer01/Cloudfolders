> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/weixin_42104154/article/details/113628184)

### 目录

*   *   [相关课程链接](#_2)
    *   [第一章 绪论](#__7)
    *   *   [知识网图](#_8)
    *   [第二章 线性表](#__10)
    *   *   [知识网图](#_12)
        *   [顺序表和链表的比较](#_15)
    *   [第三章](#_26)
    *   *   [知识网图](#_27)
        *   [区分队空或队满的方式](#_30)
        *   [栈在括号匹配中的应用](#_35)
        *   [队列在计算机系统中的应用](#_41)
    *   [第四章 串](#__46)
    *   *   [知识网图](#_47)
        *   [KMP算法](#KMP_49)
        *   [串的特点](#_56)
    *   [第五章 树与二叉树](#__62)
    *   *   [知识网图](#_63)
        *   [树的性质](#_66)
        *   [二叉树与度为2的有序树的区别](#2_73)
        *   [二叉树的性质](#_77)
    *   [第六章 图](#__85)
    *   *   [知识网图](#_86)
        *   [图的存储结构](#_88)
        *   [图的遍历](#_121)
        *   [最小生成树](#_135)
        *   [最短路径](#_145)
        *   [拓扑排序](#_157)
        *   [关键路径](#_160)
    *   [第七章 查找](#__164)
    *   *   [B树](#B_166)
        *   [B+树](#B_184)
        *   [m阶B树与m阶B+树的区别](#mBmB_193)
    *   [第八章 排序](#__201)
    *   *   [知识网图](#_202)
    *   [pdf版下载](#pdf_205)

相关课程链接
------

> [数据结构总结与知识网图](https://blog.csdn.net/weixin_42104154/article/details/113628184)  
> [计算机网络知识总结及知识网图](https://blog.csdn.net/weixin_42104154/article/details/113439733)  
> [操作系统总结及知识网图](https://blog.csdn.net/weixin_42104154/article/details/113004686)  
> [计算机组成原理总结及知识网图](https://blog.csdn.net/weixin_42104154/article/details/112854139)

第一章 绪论
------

### 知识网图

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210204104058196.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70#pic_center)

第二章 线性表
-------

### 知识网图

![在这里插入图片描述](https://img-blog.csdnimg.cn/2021020415493989.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70#pic_center)

### 顺序表和链表的比较

> **1）存取方式**  
> 顺序表可以顺序存取，也可随机存取，链表只能从表头顺序存取元素  
> **2）逻辑结构与物理结构**  
> 采用顺序存储时，逻辑上相邻的元素，对应的物理存储位置也相邻。采用链式存储时，逻辑上相邻的元素，物理存储位置不一定相邻，对应的逻辑关系通过指针链接来表示。  
> **3）查找、插入和删除操作**  
> 对于**按值查找**，顺序表无序时，两者的时间复杂度均为O(1)，顺序表有序时，可采用折半查找，时间复杂度为O(log2n).  
> 对于**按序号查找**，顺序表支持随机访问，时间复杂度为O(1),而链表的平均时间复杂度为O(n).  
> 对于**插入、删除**操作，顺序表需要移动半个表长的元素，而链表只需修改相关结点的指针域即可。

第三章
---

### 知识网图

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210204215305896.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70#pic_center)

### 区分队空或队满的方式

> 1)牺牲一个单元来区分队空和队满，入队时少用一个队列单元。即约定以“队头指针在队尾指针的下一位置作为队满的标志”。  
> 2）类型中增设表示元素个数的数据成员。  
> 3）类型中增设tag数据成员，以区分队满或队空。tag=0时，若因删除导致Q.front=Q.rear，则队空；若因插入导致Q.front=Q.rear，则队满。

### 栈在括号匹配中的应用

> **算法思想：**  
> 1）初始设置一个空栈，顺序读入括号。  
> 2）若是右括号，则或者使置于栈顶的最急迫期待得以消解，或者是不合法的情况（括号序列不匹配，则退出程序。  
> 3）若是左括号，则作为一个新的更急迫的期待压入栈中，使原有的在栈中的所有未消解的期待的急迫性降了一级。算法结束时，栈为空，否则括号序列不匹配。

### 队列在计算机系统中的应用

> 队列经常被应用于计算机系统中。  
> **1）解决主机与设备之间的速度不匹配的问题**  
> **2）解决由多用户引起的资源竞争问题**

第四章 串
-----

### 知识网图

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210204223743203.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70#pic_center)

### KMP算法

> KMP的时间复杂度为O(m+n)，直观地看，是因为在匹配过程中指针 i 没有回溯。KMP算法的核心思想是利用已经得到的部分匹配信息来进行后面的匹配过程。  
> 从主串s的第pos个字符起和模式的第一个字符比较之，若相等，继续逐个比较后继字符。当一趟匹配过程中出现字符比较不等时，不回溯指针，而是利用已经得到的“部分匹配”的结果将模式串向右“滑动”尽可能远的一段距离后，继续进行比较。  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210204224135408.png)  
> **KMP算法匹配过程**  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210204224233604.png)  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210204224225812.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)

### 串的特点

> **串的两个显著特点是：**  
> 1、它的数据元素都是字符，因此它的存储结构和线性表有很大不同，例如多数情况下，实现串类型采用的是“堆分配”的存储结构，而当用链表存储串值时，结点中数据域的类型不是“字符”，而是“串”，这种块链结构通常只在应用程序中使用；  
> 2、串的基本操作通常以"串的整体"作为操作对象，而不像线性表是以"数据元素"作为操作对象。

第五章 树与二叉树
---------

### 知识网图

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210207100639938.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70#pic_center)

### 树的性质

> 1)树中的结点数等于所有结点的度数加1.  
> 2）度为m的树中的第i层上至多m^(i-1)个结点。  
> 3）高度为h的m叉树至多有(m^h-1)/(m-1)个结点。  
> 4）具有n个结点的m叉树的最小高度为(logm(n(m-1)+1))取上限。

### 二叉树与度为2的有序树的区别

> 1）度为2的树至少有三个结点，而二叉树可以为空。  
> 2）度为2的有序树的孩子的左右次序是相对于另一孩子而言，若某一结点只有一个孩子，则无左右次序之分，而二叉树有左右次序之分。

### 二叉树的性质

> 1)在二叉树的第i层上至多有2i-1个结点（i>0）。  
> 2)深度为k的二叉树至多有2k-1个结点（k>0）。（满二叉树）  
> 3)对于任何一棵二叉树，若2度的结点数有n2个，则叶子数（n0）必定为n2＋1 （即n0=n2+1）  
> 4)具有n个结点的完全二叉树的深度必为log2n（取下限） ＋1  
> 5）: 对完全二叉树，若从上至下、从左至右编号，则编号为i 的结点，其左孩子编号必为2i，其右孩子编号必为2i＋1；其双亲的编号必为 i/2  （取下限）（i＝1 时为根,除外）

第六章 图
-----

### 知识网图

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210207230355895.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70#pic_center)

### 图的存储结构

> 根据图的自身特性给，可采取以下五种存储方式：  
> 1）邻接矩阵  
> 2）邻接表  
> 3）邻接多重表  
> 4）十字链表  
> 5）边集数组  
> **1）邻接矩阵**  
> 用两个数组来表示图，一个一维数组存储图中的顶点信息，一个二维数组（邻接矩阵）存储图中的边或弧的信息。  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209223512617.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209223541193.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209223603203.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209223643228.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)  
> **2）邻接表**  
> 数组与链表相结合的存储方法  
> 一维数组存放所有顶点信息  
> 每个顶点Vi的所有邻接点构成一个线性表，用链表存储  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209223940402.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209223959141.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209224019118.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209224044261.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)  
> **3）邻接多重表**  
> 对于无向图，一条边对应的两个顶点互为邻接点，一条边会产生两个邻接表结点，则会造成空间浪费，操作繁琐，变得删除修改均要找到两个顶点操作两次。  
> 改造边结点类型，形成一种新的结构：邻接多重表  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209224120773.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)  
> **4）十字链表**  
> 对于有向图，邻接表关注了顶点的出边，易于计算出度，入读则效率低下。而逆邻接表关注了顶点的入边，易于计算入度，但出度效率低下。  
> 将二者综合考虑，邻接表+逆邻接表，改造顶点和边结点的类型，形成一种十字链表  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/2021020922491496.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)  
> **5）边集数组**  
> 由两个一维数组组成，一个存放顶点的信息，即顶点集合，一个存放边的信息，即边集数组  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/2021020922503847.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)

### 图的遍历

> 从图中某一顶点出发访遍图中其余顶点，每个顶点仅被访问一次。  
> 两种遍历方式  
> 1）深度优先遍历  
> 2）广度优先遍历  
> **1）深度优先遍历**  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/2021020922541261.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)  
> **2）广度优先遍历**  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/2021020922552724.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)

### 最小生成树

> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209225625682.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)  
> **最小生成树性质**  
> 1）最小生成树不是唯一的。当图G中的各边权值互不相等时，G的最小生成树是唯一的；若无向连通图的边数比顶点数少1，即G本身是一棵树时，则G的最小生成树就是它本身。  
> 2）最小生成树的边的权值之和总是唯一的，且是最小的。  
> 3）最小生成树的边数为顶点数-1。  
> **实现算法：**  
> 1）Prim算法  
> 2）Kruskal算法

### 最短路径

> 对于网图，最短路径是两个顶点之间经过的边上权值之和最小的路径  
> 路径上的第一个顶点是原点  
> 路径上最后一个顶点是终点  
> **最短路径问题**  
> 1）单源最短路径问题  
> **Dijkstra算法**  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209230118601.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)

> 2）任意两点间最短路径问题  
> **Floyd算法**  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209230159444.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)

### 拓扑排序

> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209230242375.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209230300137.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)

### 关键路径

> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209230340837.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209230413547.png)

第七章 查找
------

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209230856510.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70#pic_center)

### B树

> **B树的性质**  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209231142734.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)  
> **B树的查找**  
> 从根结点出发，先在结点上折半查找k，若找到，则查找成功，否则  
> 若Ki<K<Ki+1，则沿Ai子树继续查找；  
> 若K>Kn,则沿An子树继续查找；  
> 若已到达叶子结点，则查找失败。  
> **B树的插入（分裂调整）**  
> 通过查找操作，定位待插入的结点，再向结点上插入新记录。若结点中记录个数超过m-1个，则进行分裂调整。  
> 将结点的中间记录抽出，将结点分裂为两个结点  
> 将中间记录加入到其父结点中  
> 继续对父结点做出调整，当根结点被分裂调整后，生成新的根结点  
> **B树的删除**  
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209231808202.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70)

### B+树

> B+树是应数据库所需而出现的一种B树的变形树。  
> 一棵m阶B+树所满足的条件：  
> 1）每个分支结点最多有m颗子树（孩子结点）。  
> 2）非叶根结点至少有两棵子树，其他每个分支结点至少有[m/2]颗子树。  
> 3）结点的子树个数与关键字个数相等。  
> 4）所有叶结点个数与关键字个数相等。  
> 5）所有分支结点中仅包含它的各个子结点中关键字的最大值及指向其子结点的指针。

### m阶B树与m阶B+树的区别

> 1）在B+树中，具有n个关键字的结点只含有n颗子树，即每个关键字对应一棵子树；在B树中，具有n个关键字的结点含有n+1颗子树。  
> 2）在B+树中，每个结点（非根内部结点）的关键字个数n的范围是[m/2]<=n<=m（根结点：1<=n<=m);在B树中，每个结点（非根内部结点）的关键字n的范围为[n/2]-1<=n<=m)(根结点：1<=n<=m-1)。  
> 3）在B+树中，叶结点包含信息，所有非叶结点仅起索引作用，非叶结点中的每个索引项只含有对应子树的最大关键字和指向该子树的指针，不含有该关键字对应记录的存储地址。  
> 4）在B+树中，叶结点包含全部关键字，即在非叶结点中出现的关键字也会出现在叶结点中；在B树中，叶结点包含的关键字和其他结点包含的关键字是不重复的。  
> 5）B+树可以进行顺序查找，B树不支持顺序查找。

第八章 排序
------

### 知识网图

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209234206764.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70#pic_center)## 知识网图  
链接: [https://download.csdn.net/download/weixin_42104154/16486739](https://download.csdn.net/download/weixin_42104154/16486739).

pdf版下载
------

pdf下载链接已经放在文末，大家可以点链接下载，个人总结，仅供学习参考，勿商用  
[https://download.csdn.net/download/weixin_42104154/85783343](https://download.csdn.net/download/weixin_42104154/85783343)