> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/love521314123/article/details/122825247)

### [计算机组成原理](https://so.csdn.net/so/search?q=%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BB%84%E6%88%90%E5%8E%9F%E7%90%86&spm=1001.2101.3001.7020)

*   *   [1.计算机系统概述](#1_1)
    *   *   [1. 计算机发展历程](#1__3)
        *   [2.计算机系统的组成](#2_7)
        *   [3.存储器](#3_25)
        *   [4.运算器](#4_42)
        *   [5. 控制器](#5__46)
        *   [6. 计算机的工作过程（重点）](#6__50)
        *   [7. 计算机的层次结构](#7__68)
        *   [8.计算机的性能指标](#8_80)
        *   *   [1. 存储器](#1__82)
            *   [2. CPU](#2_CPU_86)
            *   [3.系统整体的性能指标](#3_96)
            *   [4. 思考](#4__100)
    *   [2. 数据的表示和运算](#2__104)
    *   *   [1.进位计数制](#1_106)
        *   [2.BCD码](#2BCD_132)
        *   [3. 字符与字符串](#3__153)
        *   [4.奇偶校验码](#4_171)
        *   [5.海明码](#5_185)
        *   [6. 循环冗余校验码（CRC码）](#6_CRC_204)
        *   [7. 定点数的表示](#7__220)
        *   [8.移位运算](#8_254)
        *   [9. 溢出判断](#9__276)
        *   [10.原码乘法运算](#10_284)
        *   [11.补码乘法运算](#11_290)
        *   [12.原码除法运算](#12_300)
        *   [13.补码除法运算](#13_314)
        *   [14.强制类型转换](#14_318)
        *   [15.数据的存储和排列](#15_322)
        *   [16. 浮点数的表示](#16__332)
        *   [17. IEEE 754 浮点数标准](#17_IEEE_754__344)
        *   [18.浮点数的运算](#18_366)
        *   [19. 电路的基本原理](#19__384)
    *   [3.存储系统](#3_394)
    *   *   [1. 主存简单模型和寻址概念](#1__396)
        *   [2.存储器RAM](#2RAM_406)
        *   [3.ROM(只读存储器)](#3ROM_416)
        *   [4.存储器基本概念](#4_424)
        *   [5. 主存与CPU的连接](#5_CPU_442)
        *   [6.主存与CPU的连接（例题）](#6CPU_459)
        *   [7.双端口RAM和多模块存储器](#7RAM_469)
        *   [8.局部性原理及性能分析](#8_487)
        *   [9. Cache 地址映射](#9_Cache__501)
        *   [10.cache替换算法及写策略](#10cache_519)
        *   [11. 虚拟存储器](#11__551)
    *   [4.指令系统](#4_573)
    *   *   [1.指令格式](#1_575)
        *   [2.指令寻址](#2_605)
        *   [3.数据寻址1](#31_615)
        *   [4.数据寻址2——偏移寻址](#42_657)
        *   [5. 数据寻址——堆栈寻址](#5__679)
        *   [6.CISC和RISC](#6CISCRISC_683)
    *   [5.中央处理器](#5_693)
    *   *   [1.CPU功能和基本结构](#1CPU_695)
        *   [2.指令周期的数据流](#2_719)
        *   [3. 数据通路1——CPU内部单总线通路](#3_1CPU_745)
        *   [4. 数据通路2——专用数据通路](#4_2_775)
        *   [5. 控制器1——硬布线](#5_1_807)
        *   [6.控制器2——微程序](#62_821)
        *   [7.指令流水线的概念及性能指标](#7_873)
        *   [8.影响流水线的因素及分类](#8_899)
    *   [6.总线](#6_955)
    *   *   [1.总线的概念和分类](#1_957)
        *   [2.性能指标](#2_993)
        *   [3. 总线仲裁](#3__1013)
        *   [4. 总线操作和定时](#4__1041)
        *   [5. 总线标准](#5__1069)
    *   [7. 输入输出系统](#7__1075)
    *   *   [1. IO系统基本概念](#1_IO_1077)
        *   [2. 输入输出](#2__1091)
        *   [3. 外存储器](#3__1101)
        *   [4. IO接口](#4_IO_1125)
        *   [5. 程序查询方式](#5__1147)
        *   [6. 中断系统](#6__1165)
        *   [7. 程序中断方式](#7__1211)
        *   [8. DMA方式](#8_DMA_1229)

1.计算机系统概述
---------

### 1. 计算机发展历程

![image-20220124155140426](https://img-blog.csdnimg.cn/img_convert/02a710dc677a4aeb46c57a3fa3d8989a.png)

### 2.计算机系统的组成

*   冯诺依曼体系结构：以运算器为核心

![image-20220124155439445](https://img-blog.csdnimg.cn/img_convert/0d742dfebdb1ecb04e4064161f067207.png)

*   冯诺依曼体系结构的特点

![image-20220124163921396](https://img-blog.csdnimg.cn/img_convert/44eec20e497534bd818ef08472a396b8.png)

*   现在计算机体系结构：以内存为核心

![image-20220124155514424](https://img-blog.csdnimg.cn/img_convert/d09d3489652ef1429feae311861ccf9e.png)

*   CPU，主机，外设

![image-20220124155601121](https://img-blog.csdnimg.cn/img_convert/6cc37c8878488314eacda92998e54616.png)

### 3.存储器

*   主存储器由存储体，MAR，MDR组成
*   和右边的图进行类比，MAR存储CPU想要获取数据的地址，在存储体中找到后放在MDR中，CPU从MDR中把数据取走。

![image-20220124161217722](https://img-blog.csdnimg.cn/img_convert/f68eea908c0096c58553543d9665a4bb.png)

*   存储体是由一个个[存储单元](https://so.csdn.net/so/search?q=%E5%AD%98%E5%82%A8%E5%8D%95%E5%85%83&spm=1001.2101.3001.7020)组成的
    
*   存储字：存储单元中二进制代码的集合
    
*   存储字长：存储单元中二进制代码的位数
    

![image-20220124161625621](https://img-blog.csdnimg.cn/img_convert/7acde24209c1b10b3379eb779c000236.png)

### 4.运算器

![image-20220124162029858](https://img-blog.csdnimg.cn/img_convert/8c5124abda8b51f5383bb39c0e2fc798.png)

### 5. 控制器

![image-20220124162149845](https://img-blog.csdnimg.cn/img_convert/af03fabce192609ca3ed350b03be6122.png)

### 6. 计算机的工作过程（重点）

*   程序被编译成二进制存储在主存中

![image-20220124162251737](https://img-blog.csdnimg.cn/img_convert/c113fde7332d03c5c6c7d400d4d79bf9.png)

> 工作过程

*   （MAR）：表示MAR里边的值为0
    
*   M(MAR) ：主存储器所指向的存储单元里边的值
    
*   OP（IR）：取操作码
    
*   Ad（IR）：取地址码
    

![image-20220124162438267](https://img-blog.csdnimg.cn/img_convert/0d9c2d68262a80f4fa80595623d62d5d.png)

![image-20220124163303409](https://img-blog.csdnimg.cn/img_convert/a1673e01ad3e109d5f03afaa038b208e.png)

### 7. 计算机的层次结构

![image-20220124164821189](https://img-blog.csdnimg.cn/img_convert/c05bd84fd952372bdbadceb6c90742ed.png)

*   注意编译程序和解释程序的区别

编译程序:将高级语言编写的源程序全部语句一次全部翻译成机器语言程序，而后再执行机器语言程序（只需翻译一次)

解释程序将源程序的一条语句翻译成对应于机器语言的语句，并立即执行。紧接着再翻译下一句(每次执行都要翻译)

![image-20220124164939418](https://img-blog.csdnimg.cn/img_convert/db91312669c9c643d5793cbb6c39ad96.png)

### 8.计算机的性能指标

#### 1. 存储器

![image-20220124165253241](https://img-blog.csdnimg.cn/img_convert/2e48d9ad8d1e09f14110519e9b98bbf8.png)

#### 2. CPU

![image-20220124170445476](https://img-blog.csdnimg.cn/img_convert/35961aa013861c4f3dfc295df302bfb9.png)

![image-20220124170634769](https://img-blog.csdnimg.cn/img_convert/5a609bde1d19810e6f9a1a1b3c301d57.png)

#### 3.系统整体的性能指标

![image-20220124170834659](https://img-blog.csdnimg.cn/img_convert/f9c41c015f846bc3a03799885986f825.png)

#### 4. 思考

![image-20220124171228641](https://img-blog.csdnimg.cn/img_convert/ca2000736b8e25a38198436d22b4761c.png)

2. 数据的表示和运算
-----------

### 1.进位计数制

*   其他进制转十进制

![image-20220124172254378](https://img-blog.csdnimg.cn/img_convert/76b5829c5c4a002e3b6e0725eadaa15a.png)

*   二进制<——> 八进制，十六进制 (注意：小数部分也是从右往左算)

![image-20220124172619709](https://img-blog.csdnimg.cn/img_convert/70bce46b02cbff05a0dee21a62ca1d6c.png)

*   十进制——>任意进制（整数部分）

![image-20220124192353762](https://img-blog.csdnimg.cn/img_convert/d630b11c2ebe1373fbcdad4789359d00.png)

*   十进制——>任意进制（小数部分）

![image-20220124192439652](https://img-blog.csdnimg.cn/img_convert/1962e0e7ae094806aec8f9a42327dfc9.png)

*   十进制转二进制（拼凑法，适用于十进制数不是很大的情况）

![image-20220124192728894](https://img-blog.csdnimg.cn/img_convert/0af86154a6252fdbcfe74795eb658f87.png)

*   真值和机器数

![image-20220124192704256](https://img-blog.csdnimg.cn/img_convert/bfb591fa8b1feba075a98f8dc8963343.png)

### 2.BCD码

*   概念

![image-20220126171803519](https://img-blog.csdnimg.cn/img_convert/284b13dd902e31e7a16256ec8f0dff76.png)

*   8421码

![image-20220126171920070](https://img-blog.csdnimg.cn/img_convert/5af9efeb92a0395784cfaf676a7184e2.png)

*   8421码相加

1.  可以转换成十进制相加后，再转换成8421码
2.  机算方法：不在范围内，加6。如图所示

![image-20220126172432712](https://img-blog.csdnimg.cn/img_convert/2c88f12b4d17df8062e3c519256efef6.png)

*   其他表示方式

![image-20220126174706248](https://img-blog.csdnimg.cn/img_convert/d775879b3681a6a167b3f227728b26d0.png)

### 3. 字符与字符串

*   ASCII码

![image-20220126180204687](https://img-blog.csdnimg.cn/img_convert/b192b4d6a8969cf0b80c90fb5b39318d.png)

*   汉字的表示和编码

![image-20220126180314162](https://img-blog.csdnimg.cn/img_convert/d0606334df791d89bbdbdb8eee5cf174.png)

*   字符串的表示形式

![image-20220126180403191](https://img-blog.csdnimg.cn/img_convert/ead70133284d8954e91d1ce8222c0930.png)

*   知识回顾

![image-20220126180437047](https://img-blog.csdnimg.cn/img_convert/67af3ff025a022aca5010fc0a56abc6c.png)

### 4.奇偶校验码

*   校验原理

![image-20220126180907544](https://img-blog.csdnimg.cn/img_convert/abf6b9c8e685c652fcc436d397aa9124.png)

*   奇偶校验码

![image-20220126181124538](https://img-blog.csdnimg.cn/img_convert/db82eb0dda2d50492d8d5480706bc78e.png)

*   硬件实现

![image-20220126192604899](https://img-blog.csdnimg.cn/img_convert/0077fc747242d5ee263d3aeb2155c5a5.png)

### 5.海明码

*   设计思想

![image-20220126192014802](https://img-blog.csdnimg.cn/img_convert/d5c3e653cd52a0128b9600575afc86a5.png)

*   求解步骤

![image-20220126195838236](https://img-blog.csdnimg.cn/img_convert/33ff3e364df54c0f723e8720103e8dc9.png)

![image-20220126193248739](https://img-blog.csdnimg.cn/img_convert/0bbdc09794447efebdf3260bf2d5c5a8.png)

*   全校验

1.  海明码只能纠错一位（一个数据传错时，可以纠正）
2.  可以检错两位

![image-20220126195918658](https://img-blog.csdnimg.cn/img_convert/cf2d2120a4b5e16a27eaf3ea00030811.png)

### 6. 循环冗余校验码（CRC码）

*   基本思想

![image-20220126200208426](https://img-blog.csdnimg.cn/img_convert/fd865ebcc58b996325bda3a3ca10b25c.png)

*   例题

[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-TxXHrXvO-1644306008648)(C:\Users\86155\AppData\Roaming\[Typora](https://so.csdn.net/so/search?q=Typora&spm=1001.2101.3001.7020)\typora-user-images\image-20220126201152982.png)]

![image-20220126202544654](https://img-blog.csdnimg.cn/img_convert/65d2af0eb9f902bd379b23081072e5b9.png)

*   CRC校验码计算过程

![image-20220126202718290](https://img-blog.csdnimg.cn/img_convert/d441a84b2f302233f75ba534afd0bb1d.png)

### 7. 定点数的表示

*   定点数和浮点数的概念

![image-20220127144253289](https://img-blog.csdnimg.cn/img_convert/f44b40864ec58946b471be7dc35cc79b.png)

*   无符号数

![image-20220127144714178](https://img-blog.csdnimg.cn/img_convert/73817f209a92e820eef643db4c867011.png)

*   原码

![image-20220127145309171](https://img-blog.csdnimg.cn/img_convert/59fb3a03fc275ce5e5333a30d769fa0c.png)

*   反码

![image-20220127145448551](https://img-blog.csdnimg.cn/img_convert/77c9db0581910657f44d1964ed07c331.png)

*   补码(高频考点)

![image-20220127150050213](https://img-blog.csdnimg.cn/img_convert/5daed5d8076559abc4a911fd285b9277.png)

*   移码

![image-20220127150230867](https://img-blog.csdnimg.cn/img_convert/a59cc0ea2e5bdb5b7eefbabf10825f1d.png)

*   技巧

![image-20220127150633042](https://img-blog.csdnimg.cn/img_convert/77565155a6ba1ab85593bb2ce70c38e0.png)

*   补码的作用（注意：执行加法运算时，符号位一起参加运算）

![image-20220127152758634](https://img-blog.csdnimg.cn/img_convert/56d1878a71fe4999ffbdb3349235e41f.png)

### 8.移位运算

*   原码的算数移位

![image-20220127153359639](https://img-blog.csdnimg.cn/img_convert/feba8c10befb09b3bcc1f255901a2852.png)

*   反码的算数移位

![image-20220127153607298](https://img-blog.csdnimg.cn/img_convert/029151dcfd30f6b1a83d6e136ec7fae9.png)

*   补码的算数移位

![image-20220127153830245](https://img-blog.csdnimg.cn/img_convert/b0dfd4611c62cb16cc8fcbb317cc0870.png)

*   总结

![image-20220127153942017](https://img-blog.csdnimg.cn/img_convert/ce062992ae7eb7f207f1da23725ed586.png)

*   逻辑移位

![image-20220127154131912](https://img-blog.csdnimg.cn/img_convert/e46c366d0e8fa27d54b932da55f96f34.png)

### 9. 溢出判断

![image-20220127161103371](https://img-blog.csdnimg.cn/img_convert/d0bc7fc767a3def6f90c47c48e51e4ef.png)

*   符号扩展

![image-20220127161325545](https://img-blog.csdnimg.cn/img_convert/243c3922ffd4f1eb2ced2c14d12a31fd.png)

### 10.原码乘法运算

*   机器实现（视频 P18节）

![image-20220127163743939](https://img-blog.csdnimg.cn/img_convert/78a6d46b6cfb08d73fbfaac0760f10d5.png)

### 11.补码乘法运算

*   机器实现

![image-20220127215747197](https://img-blog.csdnimg.cn/img_convert/9725aaa09c3de568822601e510897875.png)

*   手算步骤

![image-20220127215810158](https://img-blog.csdnimg.cn/img_convert/281c62665c158815b5262af7436e8d6d.png)

### 12.原码除法运算

*   机器运算过程

![image-20220128125621231](https://img-blog.csdnimg.cn/img_convert/ded52c58ba10c98b23733febae1b3619.png)

*   恢复余数法

![image-20220128131154037](https://img-blog.csdnimg.cn/img_convert/83b84c96e274adbb91a6e1a7cf57bfef.png)

*   加减交替法

![image-20220128131225276](https://img-blog.csdnimg.cn/img_convert/ef636573ba7e44f3a8f2329004a56c5c.png)

### 13.补码除法运算

![image-20220128130246826](https://img-blog.csdnimg.cn/img_convert/89e42a4e83a55d0c93db4cffd827a76e.png)

### 14.强制类型转换

![image-20220128131830289](https://img-blog.csdnimg.cn/img_convert/fe4e9e607725a012bf889eac83020997.png)

### 15.数据的存储和排列

*   大小端模式

![image-20220128132209812](https://img-blog.csdnimg.cn/img_convert/70c30e4e6eba63bca5aaca0ed620175e.png)

*   边界对齐

![image-20220128141621511](https://img-blog.csdnimg.cn/img_convert/383ef119b26cce46beb66b29f3e64bc7.png)

### 16. 浮点数的表示

*   浮点数的表示

![image-20220128144507292](https://img-blog.csdnimg.cn/img_convert/3f004271ffb074d29a89097f7f692c19.png)

*   尾数的规格化

![image-20220128144600960](https://img-blog.csdnimg.cn/img_convert/beda3a665f18598df6efd691863b7123.png)

![image-20220128144703337](https://img-blog.csdnimg.cn/img_convert/9f2e640dd5fe0f0835d07bdd6a23ad75.png)

### 17. IEEE 754 浮点数标准

*   标准

![image-20220128145831536](https://img-blog.csdnimg.cn/img_convert/d7dab764cc8be22585efb3eea2b3d638.png)

*   示例（十进制转换为浮点数）

![image-20220128150220191](https://img-blog.csdnimg.cn/img_convert/e5715df560c9d84606aec8d7d16c3a50.png)

*   示例（浮点数转换为十进制数）

![image-20220128150436743](https://img-blog.csdnimg.cn/img_convert/1571af1358f0063996617047dc45e43b.png)

*   单精度浮点数表示的最大值，最小值

![image-20220128150646292](https://img-blog.csdnimg.cn/img_convert/99a90a5c0aeb7cfae67effd64b7185b1.png)

*   特殊数值

![image-20220128151026706](https://img-blog.csdnimg.cn/img_convert/83c20f87d1edcf4162cc3b9c04575c53.png)

### 18.浮点数的运算

*   和十进制的科学计数法进行类比

![image-20220128152136960](https://img-blog.csdnimg.cn/img_convert/1cbece81e03f93d69e2b7b0643192608.png)

*   浮点数加减法（P26）

![image-20220128154425894](https://img-blog.csdnimg.cn/img_convert/7d6dde27997a8eecb1da0bb355d926ac.png)

*   舍入

![image-20220128155152407](https://img-blog.csdnimg.cn/img_convert/f80c7a91e8efe65cbcf6d055b96c6e7c.png)

*   强制类型转换

![image-20220128155130204](https://img-blog.csdnimg.cn/img_convert/e4d37e1734a0490dac5242ee752764e2.png)

### 19. 电路的基本原理

*   基本的逻辑运算

![image-20220128160058822](https://img-blog.csdnimg.cn/img_convert/68b8dae05c7ede4993032ee4e3db0da2.png)

*   复合逻辑

![image-20220128160542357](https://img-blog.csdnimg.cn/img_convert/b0677889bbf3665b2f1a1857b4c57686.png)

3.存储系统
------

### 1. 主存简单模型和寻址概念

*   存储器芯片的基本结构

![image-20220130152344905](https://img-blog.csdnimg.cn/img_convert/423b74ad7e7e08968578560d6bd96d31.png)

*   寻址

![image-20220130153001312](https://img-blog.csdnimg.cn/img_convert/003d51260e7bad7114d37b17f5c9ee21.png)

### 2.存储器RAM

*   两种RAM的比较

![image-20220130154140182](https://img-blog.csdnimg.cn/img_convert/17560478b446da55fc278e4bf9a93354.png)

*   DRAM的刷新![image-20220130154625070](https://img-blog.csdnimg.cn/img_convert/baebd71847dbe523dfa73d507356e353.png)

![image-20220130155833007](https://img-blog.csdnimg.cn/img_convert/5728d02dd8306c5e454e0d9d918793c3.png)

### 3.ROM(只读存储器)

*   为什么需要ROM？

因为RAM里面的数据容易丢失。

![image-20220130160929183](https://img-blog.csdnimg.cn/img_convert/be79e376b083e15a08a798c44148a926.png)

### 4.存储器基本概念

*   存储器的分类

![image-20220130161242889](https://img-blog.csdnimg.cn/img_convert/e19327ba563202f16647ab96cc14f031.png)

![image-20220130161406470](https://img-blog.csdnimg.cn/img_convert/83c86d359338b14ddb49fa3a73f6f86f.png)

*   性能指标

数据的宽度：在一个存储周期中存储的位数

![image-20220130161648937](https://img-blog.csdnimg.cn/img_convert/f2d8db9bf23cdec9cad89cae71af1341.png)

*   层次化结构

![image-20220130161822725](https://img-blog.csdnimg.cn/img_convert/9cec0f570f2bf7a9116f1fdecf1a73da.png)

### 5. 主存与CPU的连接

*   CS：片选线（决定主存是否工作）这种写法是高电平有效
*   WE：读写控制线
*   A0~A13：地址线
*   D0~D7：数据线

![image-20220130162636865](https://img-blog.csdnimg.cn/img_convert/68259062c7825a0fe6ef511ef258f423.png)

*   译码器

![image-20220130163242147](https://img-blog.csdnimg.cn/img_convert/ee2e2431ecfb8b6eb5ed8b8e1c3dc85f.png)

*   线选法和译码线选法的区别

![image-20220130164058401](https://img-blog.csdnimg.cn/img_convert/c3d1919bb0c5329a009395701c3722c8.png)

### 6.主存与CPU的连接（例题）

*   分析

![image-20220130165155365](https://img-blog.csdnimg.cn/img_convert/d6b19c970b4c0d39dfbc865273f481cc.png)

*   图解

![image-20220130165622310](https://img-blog.csdnimg.cn/img_convert/e96610eb020b5c068e0d62b746ccd510.png)

### 7.双端口RAM和多模块存储器

*   双端口RAM

![image-20220130170115628](https://img-blog.csdnimg.cn/img_convert/0520fd6af1b5b45788fc3755538256e1.png)

*   多模块存储器

![image-20220130170354942](https://img-blog.csdnimg.cn/img_convert/9e88f85a59961a2f558d07b164208187.png)

*   高位交叉编址和低位交叉编址

![image-20220130171004832](https://img-blog.csdnimg.cn/img_convert/6ce2ca6e1b6c894a3745d7346d108e8f.png)

*   流水线问题

![image-20220130171717868](https://img-blog.csdnimg.cn/img_convert/3a737ac8ddb6ab4948968973a02b57dc.png)

### 8.局部性原理及性能分析

*   局部性原理

![image-20220130173154035](https://img-blog.csdnimg.cn/img_convert/1ee585f3fe89769c88c71948ff3f3c52.png)

*   性能分析

![image-20220130173324687](https://img-blog.csdnimg.cn/img_convert/fe4361526bff45580c95e54900646a14.png)

*   例题（蓝色字体为答案）

![image-20220130173700544](https://img-blog.csdnimg.cn/img_convert/37eb0beab3cf0f5d54050b68dbb7a9c0.png)

### 9. Cache 地址映射

*   Cache的工作原理

![image-20220131103221888](https://img-blog.csdnimg.cn/img_convert/74ea13954ee570d59f029025080582e4.png)

*   地址映射——全相连映射

![image-20220131103738879](https://img-blog.csdnimg.cn/img_convert/9a60d0f599f53932bd4991a7741f77d4.png)

*   地址映射——直接映射

![image-20220131104100785](https://img-blog.csdnimg.cn/img_convert/49ae7e29dcd06d79dbdfd96bac3beb8e.png)

*   地址映射——组相连映射

![image-20220131104445504](https://img-blog.csdnimg.cn/img_convert/400e4fa5b9577c7402ce176e25084f23.png)

### 10.cache替换算法及写策略

*   替换算法

LRU侧重于近期表现，LFU侧重于全局表现

![image-20220131105043802](https://img-blog.csdnimg.cn/img_convert/7e93085202817fd85045421151803a4a.png)

*   例题

![image-20220131110126624](https://img-blog.csdnimg.cn/img_convert/f344b92cf3683c9dd713132be62f4acf.png)

*   命中时的写策略

1.  写回法

![image-20220131110455683](https://img-blog.csdnimg.cn/img_convert/660fe68614678877b3096c872e77fedb.png)

2.  全写法

![image-20220131110555484](https://img-blog.csdnimg.cn/img_convert/cf1789c20d296cc26a4318086250c8dc.png)

*   未命中时的写策略

1.  写分配法

![image-20220131110657919](https://img-blog.csdnimg.cn/img_convert/4cb3f213bf0102205ef0122ca249ee47.png)

2.  非写分配法

![image-20220131110744533](https://img-blog.csdnimg.cn/img_convert/90d2a4c66bc6f3c384a30d8ca10d9cdb.png)

### 11. 虚拟存储器

*   概念

![image-20220131111953580](https://img-blog.csdnimg.cn/img_convert/30998481e1537c790c70d8119f204fd4.png)

*   页式虚拟存储器

![image-20220131112322122](https://img-blog.csdnimg.cn/img_convert/c8d41a23e97320cc84215244d117c8e8.png)

*   段式虚拟存储器

![image-20220131112408107](https://img-blog.csdnimg.cn/img_convert/0af91f965dc52a1f06dea16639f0415a.png)

*   段页式虚拟存储器

![image-20220131112443405](https://img-blog.csdnimg.cn/img_convert/c1815e1e31586719ec49f66eec404198.png)

*   快表

![image-20220131112516038](https://img-blog.csdnimg.cn/img_convert/93b54bcfe8c938298a9b1a8c85d37768.png)

4.指令系统
------

### 1.指令格式

*   指令的含义

![image-20220131112840832](https://img-blog.csdnimg.cn/img_convert/02bbdd7b906ebb9cfef1fa4bb67e79a3.png)

*   指令的格式

![image-20220131113124046](https://img-blog.csdnimg.cn/img_convert/10f052685bd16d5982bc2898eac5f1ce.png)

*   地址码

![image-20220131113711077](https://img-blog.csdnimg.cn/img_convert/d7b67fa0e0cee9fa562480625db7dce2.png)

*   扩展操作码举例

![image-20220131114025995](https://img-blog.csdnimg.cn/img_convert/2be54ac08a4a9341db64af49fc99f291.png)

*   扩展操作码的规范

![image-20220131114229234](https://img-blog.csdnimg.cn/img_convert/9f01306f3784475e39097f5e936f2c98.png)

*   指令操作码

![image-20220131114639178](https://img-blog.csdnimg.cn/img_convert/1fe15c5378b3d4c28371da2d9879fdcd.png)

*   操作类型

![image-20220131114747086](https://img-blog.csdnimg.cn/img_convert/6d9c84e38626ccc27582c02fd47e96ba.png)

### 2.指令寻址

*   数据存放

![image-20220131115415882](https://img-blog.csdnimg.cn/img_convert/00a70ced4248a902180b127168f446c3.png)

*   指令寻址

![image-20220131120018553](https://img-blog.csdnimg.cn/img_convert/4c46b30a75623eaaf91a7fdf0d68c1b9.png)

### 3.数据寻址1

*   操作数类型

![image-20220203160315336](https://img-blog.csdnimg.cn/img_convert/0a5c3da8ee73de4a4f105a15b8679d65.png)

*   地址码的构成

寻址特征：采用哪一种方式进行寻址

**通过寻址特征和形式地址求出有效地址**

![image-20220203160601853](https://img-blog.csdnimg.cn/img_convert/99f7120999049c27aa5be090c260f3af.png)

*   立即寻址

![image-20220203160950788](https://img-blog.csdnimg.cn/img_convert/f97ef6551888a49a4c9cd5166bedacc3.png)

*   直接寻址

![image-20220203161136445](https://img-blog.csdnimg.cn/img_convert/8ca4c770a2f12ae2fe2cc3614224f05d.png)

*   间接寻址

![image-20220203161401565](https://img-blog.csdnimg.cn/img_convert/c84cb527ed7348b60f60c4ce857b1b20.png)

*   寄存器寻址

![image-20220203161526792](https://img-blog.csdnimg.cn/img_convert/863a1789926d860246fafe3f77c053eb.png)

*   寄存器间接寻址

![image-20220203161628168](https://img-blog.csdnimg.cn/img_convert/88c0a67f0ad5d5ed2373f72ca4279980.png)

*   隐含寻址

![image-20220203161742257](https://img-blog.csdnimg.cn/img_convert/84f97ceb329a64262036babbd7b0f8e4.png)

*   总结

![image-20220203161816204](https://img-blog.csdnimg.cn/img_convert/eab5e612e236b278726765295e05d51c.png)

### 4.数据寻址2——偏移寻址

*   基址寻址

![image-20220203162240926](https://img-blog.csdnimg.cn/img_convert/0839dbe971032805d3488a5567e07c7c.png)

*   变址寻址

![image-20220203163048908](https://img-blog.csdnimg.cn/img_convert/2aff49fbb7e7942d7cb5f857e3522971.png)

*   相对寻址

![image-20220203163432186](https://img-blog.csdnimg.cn/img_convert/bc35823a6ef7117bfaa7225b54ac1d51.png)

*   相对寻址举例

![image-20220203164528487](https://img-blog.csdnimg.cn/img_convert/4d3d9872e97010192d74e40210d6aca7.png)

*   总结

![image-20220203164700915](https://img-blog.csdnimg.cn/img_convert/43af5cf152cd8c7471bda7ada33847cf.png)

### 5. 数据寻址——堆栈寻址

![image-20220203165103334](https://img-blog.csdnimg.cn/img_convert/d4f1b3932ae23d9900310d877c87039a.png)

### 6.CISC和RISC

*   基本含义

![image-20220203165740882](https://img-blog.csdnimg.cn/img_convert/f93f51dc007c5d16e13e310de64b3e06.png)

*   特点

![image-20220203165907312](https://img-blog.csdnimg.cn/img_convert/476e3c268554fea1b25a175fd3913b89.png)

5.中央处理器
-------

### 1.CPU功能和基本结构

*   CPU的功能

![image-20220204141306234](https://img-blog.csdnimg.cn/img_convert/8ef54f5cd0f96218eba5d9cffd9d782c.png)

*   运算器和控制器的功能

![image-20220204141524507](https://img-blog.csdnimg.cn/img_convert/1bef490ea2a0ba7594116e0b3be37c2a.png)

*   运算器的基本结构

![image-20220204142113636](https://img-blog.csdnimg.cn/img_convert/067dd73e78e63d91db2a7109d5419ace.png)

![image-20220204142656159](https://img-blog.csdnimg.cn/img_convert/a5b52300a053e81d4807e2c9f57264dd.png)

*   控制器的基本结构

![image-20220204143337083](https://img-blog.csdnimg.cn/img_convert/729c87285927df4dc3d17473924f0454.png)

*   CPU的基本结构

![image-20220204143620270](https://img-blog.csdnimg.cn/img_convert/e91388d44a089f1e1dd985b86b7d321e.png)

### 2.指令周期的数据流

*   指令周期

![image-20220204143912635](https://img-blog.csdnimg.cn/img_convert/5231da7517bf94ccf01b583bbc3f3248.png)

*   指令周期流程

![image-20220204144244474](https://img-blog.csdnimg.cn/img_convert/37b97c4a6a7c63cd482bbd18ec64476f.png)

*   取指周期

![image-20220204144352993](https://img-blog.csdnimg.cn/img_convert/5d0865173bf37f409c72153118c5f82d.png)

*   间址周期

![image-20220204144727112](https://img-blog.csdnimg.cn/img_convert/b111933c89c971f901ade5fc2e835f93.png)

*   中断周期

![image-20220204145045629](https://img-blog.csdnimg.cn/img_convert/b72431e4a7a219f78cba3d8b62035613.png)

*   指令执行方案

![image-20220204145230729](https://img-blog.csdnimg.cn/img_convert/ce974cc705636c1da2a6e137f92f92df.png)

### 3. 数据通路1——CPU内部单总线通路

*   数据通路

![image-20220204145502071](https://img-blog.csdnimg.cn/img_convert/bf791906bc51a8494fcae4c13f58d64e.png)

*   CPU内部单总线方式

在介绍这个之前，首先区别一下系统总线和内部总线。

**内部总线**是指同一部件，如CPU内部连接各寄存器及运算部件之间的总线;

**系统总线**是指同一台计算机系统的各部件，如CPU、[内存](https://so.csdn.net/so/search?q=%E5%86%85%E5%AD%98&spm=1001.2101.3001.7020)、通道和各类l/o接口间互相连接的总线。

![image-20220204150409836](https://img-blog.csdnimg.cn/img_convert/299f7ce274c39526bf3bae0077037c00.png)

*   例题

> 取指周期

![image-20220204150745077](https://img-blog.csdnimg.cn/img_convert/e9a4fc61f7f07642d57ee3448cb2a5cd.png)

> 间址周期

![image-20220204151034301](https://img-blog.csdnimg.cn/img_convert/aecdafc3280657c24549a99760f75527.png)

> 执行周期

![image-20220204151252258](https://img-blog.csdnimg.cn/img_convert/cc42f75142a981dcf2d678f4d6d482e8.png)

### 4. 数据通路2——专用数据通路

*   取指周期

![image-20220204151703479](https://img-blog.csdnimg.cn/img_convert/eb878cd01aa9e2a77fd9a83692e1b7c5.png)

*   例题

> 第一问

![image-20220204151933329](https://img-blog.csdnimg.cn/img_convert/149506470ff9dfcd05299450739702ec.png)

> 第二问

![image-20220204152000380](https://img-blog.csdnimg.cn/img_convert/b93f8bd8a7868ba93695c23af8d835e9.png)

> 第三问

![image-20220204152313291](https://img-blog.csdnimg.cn/img_convert/d0364a58a1e7d390b4a0122e541aedc4.png)

> 第四问

![image-20220204152446588](https://img-blog.csdnimg.cn/img_convert/3db4609b1dbc21b388afbbbfb8489a96.png)

> 第五问

![image-20220204152550115](https://img-blog.csdnimg.cn/img_convert/681a71954c4ac6a92ddee62b274bedde.png)

> 第六问

![image-20220204152634574](https://img-blog.csdnimg.cn/img_convert/4c12179b1b5b56c989fc1a4a754f8f20.png)

### 5. 控制器1——硬布线

*   控制器的结构和功能

![image-20220204155824810](https://img-blog.csdnimg.cn/img_convert/004c585d0e185e5235b44bce1b1ce8ec.png)

*   控制单元的输入和输出

![image-20220204155733033](https://img-blog.csdnimg.cn/img_convert/ae935f72800910a18bb6e6f4605ec23a.png)

*   CPU的控制方式

![image-20220204155634351](https://img-blog.csdnimg.cn/img_convert/f93bb13264d6bd252ab185d135941008.png)

### 6.控制器2——微程序

*   控制器的设计思路

![image-20220204160400055](https://img-blog.csdnimg.cn/img_convert/0cdd18c80546e8d4c27eecf2176d0eae.png)

*   微程序的基本思想

![image-20220205121414411](https://img-blog.csdnimg.cn/img_convert/1915634168c52172102e2df2364da6fb.png)

*   微程序控制器的基本结构

![image-20220205121747933](https://img-blog.csdnimg.cn/img_convert/15615464947d8ce7ab5d62e3ef5e8751.png)

*   控制存储器

![image-20220205122032395](https://img-blog.csdnimg.cn/img_convert/c458dd1e10ba66483cb287a9b191b95f.png)

*   微指令的格式

![image-20220205122525266](https://img-blog.csdnimg.cn/img_convert/eef827072c42523f56fd88fb72cd0257.png)

*   微指令的编码方式

![image-20220205134043538](https://img-blog.csdnimg.cn/img_convert/609b9c92cd0e63e07c3e49926f9b98de.png)

![image-20220205134142489](https://img-blog.csdnimg.cn/img_convert/ba538019cea94c99b68e66a8631ce7b8.png)

*   微指令的地址形成方式

前两种理解，后四种了解（不重要）

![image-20220205134325290](https://img-blog.csdnimg.cn/img_convert/5c08a5b96b9719a17fe7a38b3bcc0455.png)

*   下地址方式例题

![image-20220205135318575](https://img-blog.csdnimg.cn/img_convert/2519755457bd50091d3df04bc11dc11c.png)

*   一些易混淆的概念

**指令=微程序**

**微程序由多个微指令组成**

**微指令由多个微命令组成**

**微命令是微操作的控制信号**

**微操作是微命令的执行过程**

![image-20220205135623551](https://img-blog.csdnimg.cn/img_convert/80814de282fdac2d673542871ec8dd51.png)

### 7.指令流水线的概念及性能指标

*   指令流水的定义

![image-20220205140219456](https://img-blog.csdnimg.cn/img_convert/8185ff5c2707835d8e775b74290277b6.png)

![image-20220205140757971](https://img-blog.csdnimg.cn/img_convert/1969ed1f4a2cc2ae3c132aad66357503.png)

*   流水线的表示方法

![image-20220205140709591](https://img-blog.csdnimg.cn/img_convert/d2b98f6eb2c471aeca775704d8323b68.png)

*   流水线的性能指标

1.  吞吐率

![image-20220205141557742](https://img-blog.csdnimg.cn/img_convert/cfac0068303b38656d451818f4d0d7a7.png)

2.  加速比

![image-20220205141822268](https://img-blog.csdnimg.cn/img_convert/4f02bc3e41e1ab66b95b9e60cfffc891.png)

3.  效率

![image-20220205142015561](https://img-blog.csdnimg.cn/img_convert/2758e42187a15fef6205cbfff69b4f5b.png)

### 8.影响流水线的因素及分类

*   机器周期的设置

![image-20220205142525993](https://img-blog.csdnimg.cn/img_convert/24c8d0701755fa5c3d79f42e4c06eba2.png)

*   影响流水线的因素

1.  结构相关

![image-20220205142420789](https://img-blog.csdnimg.cn/img_convert/4221835a3645c501404205e906b793aa.png)

2.  数据相关

![image-20220205142724384](https://img-blog.csdnimg.cn/img_convert/6b614c4aa27e666e7101e7bd9973a8ef.png)

*   例题

![image-20220205143035517](https://img-blog.csdnimg.cn/img_convert/fe8f8badfbe3e4d4a65ad6b9bd71e8a4.png)

*   数据相关的一些概念

RAW（read after write）：写后读

另外两个同上

![image-20220205143316267](https://img-blog.csdnimg.cn/img_convert/6a18d21b437631d877b0425c15c7d121.png)

3.  控制相关

![image-20220205143549521](https://img-blog.csdnimg.cn/img_convert/766191cc9cda386de83aa94941452803.png)

*   总结

![image-20220205143611590](https://img-blog.csdnimg.cn/img_convert/6363c466e3751710969b026b20be3e29.png)

*   流水线的分类

![image-20220205143705278](https://img-blog.csdnimg.cn/img_convert/76136dc1ad238b749353ee1985a4016e.png)

![image-20220205143723927](https://img-blog.csdnimg.cn/img_convert/9b91d39dc308ed5c0c863a642bc8505a.png)

*   流水新的多发技术

1.  超标量技术

![image-20220205143838745](https://img-blog.csdnimg.cn/img_convert/96e1f2e928899566f3c705d83a81c1c9.png)

2.  超流水技术

![image-20220205143937880](https://img-blog.csdnimg.cn/img_convert/3bf2ecbc9ab6c673b2204a094f7b8df3.png)

3.  超长指令字

![image-20220205144032581](https://img-blog.csdnimg.cn/img_convert/15d4070b9449f1bd15541c5e30f3d213.png)

6.总线
----

### 1.总线的概念和分类

*   总线的特点

![image-20220206132533972](https://img-blog.csdnimg.cn/img_convert/9f34910e789573828f796bbc6c4555e2.png)

*   总线特性

![image-20220206132827567](https://img-blog.csdnimg.cn/img_convert/c229c23f044dd4947cc99470d25961d7.png)

*   总线的分类

![image-20220207135755282](https://img-blog.csdnimg.cn/img_convert/db57a052b7c34604e0edd472a1d89f35.png)

*   串行总线与并行总线

![image-20220207135911160](https://img-blog.csdnimg.cn/img_convert/34fdb011672d31a55f47d8a4864a38b8.png)

*   按总线功能

![image-20220207145722749](https://img-blog.csdnimg.cn/img_convert/d05d3c876def28f6ef05836a356de0d3.png)

*   系统总线的结构

1.  单总线结构

![image-20220207150008889](https://img-blog.csdnimg.cn/img_convert/44c81dddc9d03a4f02d5436d403379e0.png)

2.  双总线结构

![image-20220207150221254](https://img-blog.csdnimg.cn/img_convert/b3a9e56b01eb6ce3e0e9fc977d6b440a.png)

3.  三总线结构

![image-20220207150904024](https://img-blog.csdnimg.cn/img_convert/bb65e367a83d641bf904ef31077ac3fb.png)

### 2.性能指标

![image-20220207151751475](https://img-blog.csdnimg.cn/img_convert/c2e78707f1d41fde9843446d7c70f708.png)

![image-20220207152007687](https://img-blog.csdnimg.cn/img_convert/f6b77bcf436c5d5c35b46108b259e077.png)

![image-20220207152906097](https://img-blog.csdnimg.cn/img_convert/f7059eb54f65348e8ad27c502652bb5b.png)

*   带宽例题

![image-20220207152737201](https://img-blog.csdnimg.cn/img_convert/6eadf5945673568ab81fff23690eaa1a.png)

*   上节遗留问题：串行总线和并行总线哪个速度更快

![image-20220207152646974](https://img-blog.csdnimg.cn/img_convert/1e1ec43570b543626f2c025d3d94478f.png)

*   总结

![image-20220207153237319](https://img-blog.csdnimg.cn/img_convert/e7514f1e2ad780ca121af19da83f2c02.png)

### 3. 总线仲裁

*   基本特点

![image-20220207153156272](https://img-blog.csdnimg.cn/img_convert/95c142936a186720034b45e0a530590c.png)

*   集中仲裁方式（重要）

1.  链式查询方式

![image-20220207153710538](https://img-blog.csdnimg.cn/img_convert/b23048ea9ef6cf64740f41fa50ba4a37.png)

2.  计数器查询方式

![image-20220207154102188](https://img-blog.csdnimg.cn/img_convert/80e9e8f54ed80d2f506ae2e7130f9d1c.png)

3.  独立请求方式

![image-20220207154404507](https://img-blog.csdnimg.cn/img_convert/723b4d633bd33db8c07e2a09f4876ec8.png)

*   三种方式总结

![image-20220207154449055](https://img-blog.csdnimg.cn/img_convert/d5b36c4d6101191de00767ac82dab06e.png)

*   分布仲裁方式（了解即可）

![image-20220207154559945](https://img-blog.csdnimg.cn/img_convert/e7061c4e1d63d041f961a24624c52d71.png)

### 4. 总线操作和定时

*   总线传输的四个阶段

![image-20220207160527516](https://img-blog.csdnimg.cn/img_convert/59b7d88403fb4791a062b2bdfbd92962.png)

*   同步定时方式

![image-20220207160831129](https://img-blog.csdnimg.cn/img_convert/c3937f5d7650f8f22d65dde91830204c.png)

*   异步定时方式

![image-20220207161255282](https://img-blog.csdnimg.cn/img_convert/bd8f974e11d8c06aa5381c94e4119159.png)

![image-20220207161158530](https://img-blog.csdnimg.cn/img_convert/e78f836b7080ee163a6b499496c1f03f.png)

*   例题（数据传输率）

![image-20220207161520965](https://img-blog.csdnimg.cn/img_convert/9d77c6bc37e56b2aca560838667ff0f2.png)

*   半同步通信（扩展）

![image-20220207161625989](https://img-blog.csdnimg.cn/img_convert/e6325d80c76ac0af0c918c38c34d0386.png)

*   分离式通信（拓展）

![image-20220207161715786](https://img-blog.csdnimg.cn/img_convert/d7630f8bcb64c151afffeb96a6f946c9.png)

### 5. 总线标准

*   基本特点

![image-20220207162010796](https://img-blog.csdnimg.cn/img_convert/0e935e19bcdf8de4ec26280ecba6c8db.png)

7. 输入输出系统
---------

### 1. IO系统基本概念

*   演变过程

![image-20220207163204606](https://img-blog.csdnimg.cn/img_convert/ae710eeef44dd5c8e4f7eaabc7ea7fca.png)

*   IO系统基本组成

![image-20220207163129561](https://img-blog.csdnimg.cn/img_convert/b91d0fdf897af253d24a3474c6c46b35.png)

*   IO方式简介

![image-20220207163711678](https://img-blog.csdnimg.cn/img_convert/f8cfbc81913e1b8d9fa839a402ff5c7c.png)

### 2. 输入输出

*   外部设备

![image-20220208134546442](https://img-blog.csdnimg.cn/img_convert/3ec0457da7c81545c94c667f545f2fc8.png)

*   显示器

![image-20220208135025276](https://img-blog.csdnimg.cn/img_convert/f67c6e7cc671b13c37f9c6c70e063ecc.png)

### 3. 外存储器

*   基本概念

![image-20220208135334706](https://img-blog.csdnimg.cn/img_convert/cac3dd2699e1686f4bceaa5d48ed010a.png)

*   磁盘存储器

1.  磁盘设备的组成

![image-20220208135742975](https://img-blog.csdnimg.cn/img_convert/f2c8e60975b5e269e76ed2768afb8736.png)

2.  性能指标

![image-20220208140554007](https://img-blog.csdnimg.cn/img_convert/88286c7a2fdf147f8dd59b50f3316d92.png)

3.  存取时间计算过程

![image-20220208140315461](https://img-blog.csdnimg.cn/img_convert/11486e02043670684904cd4f07e848a8.png)

4.  磁盘地址和磁盘的工作过程

![image-20220208140835206](https://img-blog.csdnimg.cn/img_convert/764033bcd75c18dc3d4c2c447fa57950.png)

### 4. IO接口

*   功能

![image-20220208141144133](https://img-blog.csdnimg.cn/img_convert/aa090629d28a78a03255ceb83c919b06.png)

*   基本结构

![image-20220208141543148](https://img-blog.csdnimg.cn/img_convert/8a64bf60c12d6e33a1be70d616fb33a5.png)

*   接口与端口

![image-20220208141723953](https://img-blog.csdnimg.cn/img_convert/245786be60e5e2a66ae07663a20b411d.png)

*   IO端口及其编址

![image-20220208142103849](https://img-blog.csdnimg.cn/img_convert/ae19b5b4eec653b51c778be6398645a4.png)

*   IO接口的类型

![image-20220208142227284](https://img-blog.csdnimg.cn/img_convert/7ab2db51615070107338bc8961f66e83.png)

### 5. 程序查询方式

*   程序查询方式流程图

![image-20220208143347520](https://img-blog.csdnimg.cn/img_convert/8525ecd9f47d2021004b175cfaf5d8dd.png)

*   接口结构

![image-20220208143536105](https://img-blog.csdnimg.cn/img_convert/0a4d8bcd6b063a939d541e3ec0e0d138.png)

*   例题

![image-20220208144328807](https://img-blog.csdnimg.cn/img_convert/f309317758153751487fb239f13a55d9.png)

*   总结

![image-20220208144140914](https://img-blog.csdnimg.cn/img_convert/c93ed76afb6bb56c7ebc2ae2c0e16bba.png)

### 6. 中断系统

*   基本概念

![image-20220208144639975](https://img-blog.csdnimg.cn/img_convert/0bfba0d181ad75e2322c10e3d21f546d.png)

*   分类

![image-20220208144748709](https://img-blog.csdnimg.cn/img_convert/995e2ab13c03b36efbd8b9b93cb853c5.png)

*   中断请求标记

![image-20220208144954465](https://img-blog.csdnimg.cn/img_convert/09cd5270d6c0e2eef407a6a21c3bb82b.png)

*   中断判优

![image-20220208145216623](https://img-blog.csdnimg.cn/img_convert/6043488ff2c7980cea3c6ae5d2c1df87.png)

*   优先级设置

![image-20220208145242843](https://img-blog.csdnimg.cn/img_convert/f84916242d072e1fc5bb9cd2ce6c30c8.png)

*   中断处理过程

![image-20220208145431043](https://img-blog.csdnimg.cn/img_convert/c8cc53ddd6100b5b364855a6807f63c1.png)

*   中断隐指令

![image-20220208145809520](https://img-blog.csdnimg.cn/img_convert/ff729feb5e3ac1a8ef166617196845ac.png)

*   中断服务程序

![image-20220208145920443](https://img-blog.csdnimg.cn/img_convert/c6c09dca12b4b5c9695d12f25f95a7b4.png)

*   单重中断和多重中断

![image-20220208150150476](https://img-blog.csdnimg.cn/img_convert/b60288e78bbae841420ca3faa6bf3c63.png)

*   中断屏蔽技术

![image-20220208150354883](https://img-blog.csdnimg.cn/img_convert/59954ac309e2bc127822ce8c0625c8ed.png)

*   中断屏蔽技术 例题（重要，需掌握）

![image-20220208150716402](https://img-blog.csdnimg.cn/img_convert/74efaa3764468815effa7fd86c4df220.png)

### 7. 程序中断方式

*   程序中断方式过程

恢复现场即算做下一次启动

![image-20220208151033847](https://img-blog.csdnimg.cn/img_convert/a0490c5c7eecae8e3fa6c7d75846a713.png)

*   例题 第一问

![image-20220208151244322](https://img-blog.csdnimg.cn/img_convert/cb0142bdfb50dfeefaa96bfbd782807d.png)

*   例题 第二问 （重要）

CPI：执行一条指令所需要的时钟周期

![image-20220208151751342](https://img-blog.csdnimg.cn/img_convert/31c3db331bff6b0e750f04f788dcf5a5.png)

### 8. DMA方式

*   DMA 控制器

![image-20220208152102933](https://img-blog.csdnimg.cn/img_convert/125358f20d7d56388e1f3db8618e45e2.png)

*   结构

![image-20220208152326186](https://img-blog.csdnimg.cn/img_convert/5a3696be5efb774099514cce3c048c37.png)

*   DMA传送方式

![image-20220208152619958](https://img-blog.csdnimg.cn/img_convert/8456ff7530c051a2f81b49adc127bb12.png)

*   DMA方式的特点

![image-20220208152708447](https://img-blog.csdnimg.cn/img_convert/1345331edfc90adad64be58cb64f5de8.png)

*   DMA方式与中断方式对比

![image-20220208152756433](https://img-blog.csdnimg.cn/img_convert/642c44cc2ccb9669a4d3507c1c584e13.png)

*   CPU占用情况 中断方式

![image-20220208153306469](https://img-blog.csdnimg.cn/img_convert/0fffb63f5685a68577631bd58d2f7291.png)

*   CPU占用情况 DMA方式

![image-20220208153659050](https://img-blog.csdnimg.cn/img_convert/6c7a83dc2fa9df3c47f49cb158d07d34.png)

*   总结

![image-20220208153841685](https://img-blog.csdnimg.cn/img_convert/5b9e231dbf4abb84a4d155fda0168e07.png)