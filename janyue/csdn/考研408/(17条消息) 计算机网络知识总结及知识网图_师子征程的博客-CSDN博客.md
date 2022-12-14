> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/weixin_42104154/article/details/113439733)

### 目录

*   *   [相关课程链接](#_2)
    *   [第一章 计算机网络体系结构](#__7)
    *   *   [知识网图](#_8)
        *   [计算机网络分成的基本原则：](#_11)
        *   [TCP/IP模型和OSI参考模型的比较](#TCPIPOSI_18)
        *   [计算机网络与分布式计算机系统的主要区别](#_29)
    *   [端到端通信与点到点通信的区别](#_34)
    *   [第二章 物理层](#__40)
    *   *   [知识网图](#_41)
        *   [奈特斯特定理得到的结论](#_43)
        *   [香农定理得到的结论](#_48)
        *   [电路交换的特点](#_54)
        *   [报文交换的特点](#_68)
        *   [分组交换的特点](#_79)
        *   [数据报服务](#_90)
        *   [虚电路](#_101)
        *   [物理接口的特性](#_109)
        *   [基带传输、频带传输和宽度传输的比较](#_115)
    *   [数据链路层](#_120)
    *   *   [知识网图](#_121)
        *   [停止等待协议中可能出现差错的情况](#_124)
        *   [CSMA/CD与CSMA/CA的区别](#CSMACDCSMACA_131)
        *   [局域网的主要特点](#_137)
        *   [令牌环网中令牌和数据的传递过程](#_144)
        *   [以太网交换机的特点](#_151)
    *   [第四章 网络层](#__158)
    *   *   [知识网图](#_159)
        *   [路由与转发](#_161)
        *   [流量控制与拥塞控制](#_165)
        *   [拥塞控制的两种方法](#_175)
        *   [网络层转发分组的流程（分组转发算法）](#_181)
        *   [使用子网掩码时路由器的分组转发算法：](#_189)
        *   [地址解析协议（ARP）工作原理](#ARP_199)
        *   [DHCP交换过程](#DHCP_203)
        *   [不发送ICMP差错报告报文的情况](#ICMP_209)
        *   [ICMP询问报文的四种类型](#ICMP_215)
        *   [RIP](#RIP_221)
        *   [OSPF](#OSPF_233)
        *   [移动IP的基本通信流程](#IP_240)
    *   [第五章 传输层](#__250)
    *   *   [知识网图](#_251)
        *   [TCP连接管理](#TCP_253)
        *   [慢开始和拥塞避免](#_267)
        *   [快重传和快恢复](#_272)
    *   [第六章 应用层](#__277)
    *   *   [知识网图](#_278)
    *   [pdf版下载](#pdf_282)

相关课程链接
------

> [数据结构总结与知识网图](https://blog.csdn.net/weixin_42104154/article/details/113628184)  
> [计算机网络知识总结及知识网图](https://blog.csdn.net/weixin_42104154/article/details/113439733)  
> [操作系统总结及知识网图](https://blog.csdn.net/weixin_42104154/article/details/113004686)  
> [计算机组成原理总结及知识网图](https://blog.csdn.net/weixin_42104154/article/details/112854139)

第一章 [计算机网络](https://so.csdn.net/so/search?q=%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C&spm=1001.2101.3001.7020)体系结构
----------------------------------------------------------------------------------------------------------------------

### 知识网图

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210130164028322.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70#pic_center)

### 计算机网络分成的基本原则：

> 1)每层都实现一种相对独立的功能，降低大系统的复杂度。  
> 2）各层之间界面自然清晰，易于理解，相互交流尽可能少。  
> 3）各层功能的精确定义独立于具体的实现方法，可以采用最适合的技术来实现。  
> 4）保持下层对上层的独立性，上层单向使用下层提供的服务。  
> 5）整个分层结构应能促进标准化工作。

### TCP/IP模型和OSI参考模型的比较

> **相似点：**  
> 1）二者都采取分层的[体系结构](https://so.csdn.net/so/search?q=%E4%BD%93%E7%B3%BB%E7%BB%93%E6%9E%84&spm=1001.2101.3001.7020)，将庞大且复杂的问题划分为若干较容易处理的、范围较小的问题，而且分层的功能也大体相似。  
> 2）二者都是独立的协议栈的概念。  
> 3）二者都可以解决异构网络的互联，实现不同厂家的计算机之间的通信。  
> **不同点：**  
> 1）OSI参考模型精确定义了三个主要的概念：服务、协议和接口，这与现代面向对象程序设计思想很吻合，但TCP/IP模型并未明确区分这三个概念，不符合软件工程的思想。  
> 2）OSI模型产生在协议发明之前俺，没有偏向于任何特定的协议，通用性良好。TCP/IP模型与之相反，先出现的是协议，模型是对已有协议的描述，不会出现与协议不匹配的情况，但不适用于任何塔器非TCP/IP的协议栈。  
> 3）TCP/IP模型在设计之初就考虑到多种异构网络的互联问题，并将网际层作为一个单独的重要层次。OSI模型最初只考虑到用一种标准的公用数据网络将各种不同的系统互联。  
> 4）OSI模型在网络层支持无连接和面向连接的通信，但在传输层仅有面向连接的通信。而TCP/IP模型在网际层仅支持无连接的通信模式，但传输层支持无连接和面向连接两种模式。

### 计算机网络与分布式计算机系统的主要区别

> **分布式系统**主要的特点是，整个系统中的各个计算机对用户都是透明的。用户通过输入命令运行程序，但用户并不知道哪台计算机在为它运行程序。操作系统为用户选择一台最合适的计算机来运行其程序，并将运行的结果传送到合适的地方。  
> 而**计算机网络**，用户必须先登录欲运行程序的计算机，然后按照计算机的地址，将程序通过计算机网络传送到该计算机上运行，最后根据用户的命令将结果传送到指定的计算机。  
> 二者的区别主要在软件的不同。

端到端通信与点到点通信的区别
--------------

> **点到点通信**  
> 直接相连的结点之间的通信，只提供一台机器到另外一台机器之间的通信，不涉及程序或进程的概念。点到点通信不能保证数据传输的可靠性。  
> **端到端通信**  
> 传输层为网络中的主机提供端到端通信。端到端通信是建立在点到点通信的基础上的，是由一段段的点到点通信通道构成的，是比点到点通信更高一级的通信方式，以完成应用程序（进程）之间的通信。“端”是指用户程序的端口，端口号标识了应用层中的不同进程。

第二章 物理层
-------

### 知识网图

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210130203729712.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70#pic_center)

### 奈特斯特定理得到的结论

> 1）在任何信道中，码元传输的速率是有上限的。  
> 2）信道的频带越宽，就可用更高的速率进行码元的有效传输。  
> 3）奈氏准则给出了码元传输速率的限制，但并未对信息传输速率给出限制，即未对一个码元可以多少个二进制给出限制。

### 香农定理得到的结论

> 1）信道的带宽或信道中的信噪比越大，信息的极限传输速率越高。  
> 2）对一定的传输宽带和一定的信噪比，信息传输速率的上限是确定的。  
> 3）只要信息的传输速率低于信道的极限传输速率，就能找到某种方法来实现无差错的传输。  
> 4）香农定理得出的极限信息传输速率，实际信道能达到的传输速率要比它低不少。

### 电路交换的特点

> **优点**  
> 1）通信时延小  
> 2）有序传输  
> 3）没有冲突  
> 4）使用范围广  
> 5）实时性强  
> 6）控制简单  
> **缺点**  
> 1）建立连接时间长  
> 2）线路独占  
> 3）灵活性差  
> 4）难以规格化

### 报文交换的特点

> **优点**  
> 1）无需建立连接  
> 2）动态分配线路  
> 3）提高线路可靠性  
> 4）提高线路利用率  
> 5）提供多目标服务  
> **缺点**  
> 1）数据进入交换结点后要经历存储、转发这一过程，引起转发时延  
> 2)报文交换对报文的大小没有限制，网络结点需要较大的缓存空间

### 分组交换的特点

> 1）无建立时延  
> 2）线路利用率高  
> 3）简化了存储管理  
> 4）加速传输  
> 5）减少了出错概率和重发数据量  
> **缺点**  
> 1）存在传输时延。  
> 2）每块小数据块都需要加上源地址、目的地址和分组编号等额外信息。  
> 3）当分组交换采用数据报服务时，可能会出现失序，丢失或重复分组，分组到达目的时需要对分组按序号进行排序等工作。

### 数据报服务

> 发送端发送一个报文时，再端系统中的高层协议先将报文拆成若干带有序号的数据单元，并在网络层加上地址等控制信息后形成数据分组。中间结点存储分组很短一段时间，找到最佳路由后，尽快转发每个分组。  
> **特点：**  
> 1）发送分组前不需要建立连接。  
> 2)网络尽最大努力交付，传输不保证可靠性；为每个分组独立地选择路由，转发的路径可能不同，分组不一定按需到达目的结点。  
> 3）发送的分组中要包括发送端和接收端的完整地址，以便可以独立传输。  
> 4）分组在交换结点存储转发时，会带来一定的时延。  
> 5）网络具有冗余路径，对故障的适应能力强。  
> 6）存储转发的时延一般较小，提高网络的吞吐量。  
> 7）收发双方不独占某一链路，资源利用率较高。

### 虚电路

> 试图将数据报方式和电路交换方式结合起来，充分发挥两种方法的优点，以达到最佳的数据交换效果。再分组发送之前，要求再发送方和接收方建立一条逻辑上相连的虚电路，并且连接一旦建立，就固定了虚电路所对应的物理路径。  
> 分为三个阶段：虚电路建立，数据传输，虚电路释放  
> **特点：**  
> 1）虚电路通信链路的建立和拆除需要时间开销。  
> 2）虚电路的路由选择体现在连接建立阶段，连接建立后就确定了传输路径。  
> 3）虚电路提供了可靠的通信功能，能保证每个分组正确且有序到达。  
> 4）当网络中的某个结点或某条链路出现故障而彻底失效时，所有经过该结点或该链路的虚电路将遭到破坏。

### 物理接口的特性

> 1）机械特性。规定物理连接时所采用的规格、引线的数目、引脚的数量和排列情况等。  
> 2）电气特性。线路上信号的电压高低、阻抗匹配、传输速率何距离限制等。  
> 3）功能特性。指明某条线上出现的某一电平的电压表示何种意义，接口部件的信号线的用途。  
> 4）规程特性。主要定义各种物理线路的工作规程和时序关系。

### 基带传输、频带传输和宽度传输的比较

> **基带传输**:可以不经过调制就在信道上直接进行的传输方式，通常用于局域网。  
> **频带传输**:用数字信号对特定频率的载波进行调制，将其变成适合于传送的信号后再进行传输。  
> **宽带传输**：借助频带传输，可将链路容量分解成两个或多个信道，每个信道可以携带不同信号。

数据链路层
-----

### 知识网图

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210131215301597.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70#pic_center)

### 停止等待协议中可能出现差错的情况

> 1）数据帧丢失  
> 2）到达目的站的帧可能已遭破坏  
> 应对措施：超时重传  
> 3）数据帧正确但确认帧被破坏  
> 应对措施：超时重传，发送方将重传的同样数据帧丢弃，并重传一个对应的确认帧

### CSMA/CD与CSMA/CA的区别

> 1）CSMA/CD可以检测冲突，但无法避免；CSMA/CA发送报的同时不能检测到信道上有冲突，本结点上没有冲突不意味着在接收结点处就没有冲突，只能尽量避免。  
> 2）传输介质不同。CSMA/CD用于总线型以太网，CSMA/CA用于无线局域网。  
> 3）检测方式不同。CSMA/CD通过电缆中的电压变化来检测；CSMA/CA通过能量检测、载波检测和能量载波混合检测三种方式检测信道是否空闲。  
> 4）在本结点处有无冲突，并不意味着接收结点处就有无冲突。

### 局域网的主要特点

> 1）为一个单位所拥有，且地理范围和站点数目有限。  
> 2）所有站点共享较高的总带宽。  
> 3）较低的时延和较低的误码率。  
> 4）各站为平等关系而非主从关系。  
> 5）能进行广播和组播。

### 令牌环网中令牌和数据的传递过程

> 1）网络空闲时，环路中只有令牌帧在循环传递。  
> 2）令牌传递到有数据要发送的站点处时，该站点就修改令牌中的一个标志位，并在令牌中附加自己需要传递的数据，将令牌变成一个数据帧，然后将这个数据帧发送出去。  
> 3）数据帧沿着环路传输，接收到的站点一边转发数据，一边查看帧的目的地址。若目的地址和自己的地址相同，则接收站就复制该数据帧以便进一步处理。  
> 4）数据帧沿着环路传输，直到到达该帧的源站点，源站点接收到自己发出去的数据帧后便不再进行转发。同时发送方可以通过检验返回的数据帧来查看数据传输过程中是否有错，若有错则重传该帧。  
> 5）源站点传送完数据后，重新产生一个令牌，并将令牌传递给下一个站点，以交出对媒体的访问权限。

### 以太网交换机的特点

> 1）以太网交换机的每个端口都直接与单台主机相连，并且一般都工作在全双工方式。  
> 2）以太网交换机能同时连通多对端口，使每对相互通信的主机都能像独占通信媒体那样无碰撞传输数据。  
> 3）以太网交换机是一种即插即用的设备，其内部的帧的转发也是通过自学习自动地逐渐建立起来的。  
> 4）使用专用的交换结构芯片，交换速率较高。  
> 5）独占传输媒体的带宽。

第四章 网络层
-------

### 知识网图

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210201230217893.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70#pic_center)

### 路由与转发

> 1)路由选择。指按照复杂的分布式算法，根据从各相邻路由器所得到的关于整个网络拓扑的变化情况，动态地改变所选择的路由。  
> 2）分组转发。指路由器根据转发表将用户的IP数据报从合适的端口转发出去。

> ### 流量控制与拥塞控制
> 
> **流量控制**  
> 流量控制是发送端和接收端之间的点对点通信量的控制。流量控制所要做的是抑制发送端发送数据的速率，以便使接收端来的接收。  
> **拥塞控制**  
> 拥塞：因出现过量的分组而引起网络性能下降的现象。  
> 判断网路是否进入拥塞状态的方法是观察网络的吞吐量与网络负载的关系。若网络负载的增加，网络吞吐量明显小于正常的吞吐量，则网络已进入“拥塞“状态。  
> 确保通信子网能够待传送的数据，是一个全局性的问题，涉及网络中所有的主机、路由器及导致网络传输能力  
> 拥塞控制必须确保通信子网能够传送待传送的数据，是一个全局性的问题，涉及网络中所有的主机、路由器及导致网络传输能力下降的所有因素。

### 拥塞控制的两种方法

> **1）开环控制**  
> 在设计网络时事先将有关发送拥塞的因素考虑周到，力求网络在工作室不产生拥塞。是一种静态的预防方法。一旦整个系统启动并运行，中途就不再需要修改。  
> **2）闭环控制**  
> 事先不考虑有关发生拥塞信息传到合适的地方，采用监测网络系统去监视，及时检测哪里出现拥塞，再将拥塞信息传到合适的地方，以便调整网络系统的运行，并解决出现的问题。是基于反馈环路的，是一种动态的方法。

### 网络层转发分组的流程（分组转发算法）

> 1）从数据报的首部提取目的主机的IP地址D，得到目的地址N。  
> 2）若网络N与此路由器直接相连，则把数据报直接交付给目的主机D，即路由器的直接交付；否则是间接交付，执行3）。  
> 3）若路由表中有目的地址为D的特定主机路由，则把数据报传送给路由表中所指明的下一条路由器；否则执行4）。  
> 4）若路由表中有到达网络N的路由，则把数据报传送给路由表指明的下一跳路由器，否则，执行5）。  
> 5）若路由表中有一个默认路由，则把数据报传送给路由表中所指明的默认路由器；否则执行6）。  
> 报告转发分组出错。

### 使用子网掩码时路由器的分组转发算法：

> 1）从收到的分组的首部提取目的IP地址，记为D。  
> 2）先判断是否为直接交付。对路由器直接相连的网络逐个进行检查：用各网络的子网掩码和D逐位相”与“，看结果是否与相应的网络地址匹配。若匹配，则将分组直接交付，否则间接交付，执行3）。  
> 3）若路由表中有目的地址为D的特定主机路由，则将分组传送给路由表中所指明的下一跳路由器；否则执行4）。  
> 4）对路由表中的每一行中的子网掩码和D逐位相”与“，其结果为N。若N与该行的目的网络地址匹配，则将分组传送给该行指明的下一跳路由器；否则执行5）。  
> 5）若路由表中有一个默认路由，则将分组传送给路由表中所指明的默认路由器，否则执行6）。  
> 6）报告转发分组出错。

### 地址解析协议（ARP）工作原理

> 主机A想向本局域网上的某台主机B发送IP数据报时，先在其**ARP高速缓存**中查看有无主机B的IP地址。若有，则查出其对应的**硬件地址**，再将此硬件地址写入**MAC帧**，然后通过**局域网**将该MAC帧发往此硬件地址。若无，则通过使用目的MAC地址为FF-FF-FF-FF-FF-FF-FF的帧来封装并广播ARP请求分组，使同一个局域网里的所有主机收到ARP请求。主机B收到该ARP请求后，向主机A发出响应ARP分组，分组中包含主机B的IP与MAC地址的映射关系，主机A在收到后将此映射写入ARP缓存，然后按查询到的硬件地址发送MAC帧。

### DHCP交换过程

> 1）DHCP客户机广播“DHCP发现”消息，试图找到网络中的DHCP服务器，以便从DHCP服务器获得一个IP地址。  
> 2）DHCP服务器收到“DHCP发现”消息后，向网络中广播“DHCP提供”消息，其中包括提供DHCP客户机的IP地址和相关配置信息。  
> 3）DHCP客户机收到“DHCP提供”消息，若接收DHCP服务器所提供的相关参数，则通过广播“DHCP请求”消息向DHCP服务器请求提供IP地址。  
> 4）DHCP服务器广播“DHCP确认”消息，将IP地址分配给DHCP客户机。

### 不发送ICMP差错报告报文的情况

> 1）ICMP差错报告报文  
> 2）第一个分片的数据报片的所有后续数据报片  
> 3）具有组播地址的数据报  
> 4）具有特殊地址的数据报

### ICMP询问报文的四种类型

> 回送请求和回答报文  
> 时间戳请求和回答报文  
> 掩码地址请求和回答报文  
> 路由器询问和通告报文

### RIP

> 1)网络中的每个路由器都要维护从它自身到其他每个目的网络的距离记录。  
> 2）距离（跳数）规定从一个路由器到直接连接网络的距离为1.没经过一个路由器，则距离+1。  
> 3）RIP优先选择跳数少的路径。  
> 4）RIP规定一条路径最多包含15个路由器，RIP=16，则表示网络不可达。  
> 5）RIP默认在任意两个使用RIP的路由器之间每三十秒广播一次RIP路由更新信息，以便动态建立并维护路由表。  
> 6）在RIP中不支持子网掩码的RIP广播，所有RIP中每个网路的子网掩码必须相同。  
> **特点**  
> 1）仅与相邻路由器交换信息。  
> 2）路由器交换的信息是当前路由器所知道的全部信息，即自己的路由表。  
> 3）按固定的时间间隔交换路由信息。

### OSPF

> 1)对不同的链路可根据IP分组的不同服务类型而设置成不同的代价。  
> 2）若到同一个目的网络有多条相同代价的路径，则可以将通信量分配给这几条路径，即多路径间的负载平衡。  
> 3）所有OSPF路由器之间交换的分组都具有鉴别功能，保证了仅在可信赖的路由器之间交换链路状态信息。  
> 4）支持可变长度的子网划分和无分类编址CIDR。  
> 5）每个链路状态都带上一个32位的序号，序号越大，状态越新。

### 移动IP的基本通信流程

> 1)移动结点在本地网时，按传统的TCP/IP方式进行通信。  
> 2）移动结点漫游到一个外地网络时，仍使用固定的IP地址进行通信。为了能够接收到通信对端发给他的IP分组，移动结点需要向本地代理注册当前的位置地址，即转交地址。  
> 3）本地代理接受来自转交地址的注册后，会构建一条通向转交地址的隧道，将截获的发给移动结点的IP分组通过隧道送到转交地址处。  
> 4）在转交地址处解除隧道封装，恢复原始的IP分组，最后送到移动结点，使移动结点在外网就能够接收这些发给它们的IP分组。  
> 5）移动结点在外网通过外网的路由器或外部代理向通信对端发送IP数据包。  
> 6）移动结点在外网通过外网的路由器或外部代理向通信对端发送IP包。  
> 7）移动结点回到本地网时，移动结点向本地代理注销转交地址，此时移动结点又将使用传统的TCP/IP方式进行通信。

第五章 传输层
-------

### 知识网图

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210202114357641.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70#pic_center)

### TCP连接管理

> TCP连接分为三个阶段：连接建立，数据传输，连接释放。  
> 在TCP连接建立的过程中，要使每一方都能够确知对方的存在，允许双方协商一些参数，并能够对运输实体资源进行分配。TCP连接的建立采用客户机/服务器方式。  
> **TCP连接的建立**  
> 1）客户机的TCP首先向服务器发送一个连接请求报文段(SYN=1,seq=x)  
> 2）服务器的TCP收到连接请求报文段后，向客户机发回确认，并为该TCP连接分配TCP缓存和变量(SYN=1,ACK=1,seq=y,ack=x+1)  
> 3）当客户机收到确认报文段后，还要向服务器给给出确认，并为该连接分配缓存和变量(ACK=1,seq=x+1,ack=y+1)  
> **TCP连接的释放**  
> 1）客户机打算关闭连接时，向其TCP发送一个连接释放报文段，并停止发送数据，主动关闭TCP连接（FIN=1，seq=u)  
> 2）服务器收到连接释放报文段后即发送确认，此时，从客户机到服务器这一方向的连接被释放，TCP连接处于半关闭状态（ACK=1,seq=v.ack=u+1）  
> 3）若服务器已经没有要向客户机发送的数据，就通知TCP释放连接（FIN=1,ACK=1,seq=w,ack=u+1）  
> 4）客户机收到连接释放报文段后，必须发送确认（ACK=1,seq=u+1,ack=w+1)

### 慢开始和拥塞避免

> 使用**慢开始算法**，TCP刚连接好并开始发送TCP报文段时，先令拥塞窗口cwnd=1，即一个最大报文段长度MSS。每收到一个对新报文段的确认后，将cwnd+1，即增大一个MSS。  
> 使用**慢开始算法**后，每经过一个传输轮次，拥塞窗口cwnd会加倍，即cwnd的大小指数式增长。当拥塞窗口增大至慢开始门限后，则改用**拥塞避免算法**  
> 使用**拥塞避免算法**，发送端的拥塞窗口cwnd每经过一个往返时延RTT就增加一个MSS的大小，而不是加倍，使cwnd按线性规律缓慢增长，当出现一次超时时，令慢开始门限等于当前cwnd的一半。

### 快重传和快恢复

> **快重传技术**使用冗余确认来检测丢包的发生。同时，冗余确认也用于网络拥塞的检测。当发送方连续收到三个重复的ACK报文时，直接重传对方尚未收到的报文段，而不必等到重传计时器超时。  
> **快恢复技术**是当发送端收到连续三个冗余确认时，执行”乘法减小“算法，把慢开始门限设置为出现拥塞时发送方的一半，跳过了cwnd从1开始的慢开始过程。

第六章 应用层
-------

### 知识网图

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210202211623384.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjEwNDE1NA==,size_16,color_FFFFFF,t_70#pic_center)## 知识网图

链接: [https://download.csdn.net/download/weixin_42104154/16486720](https://download.csdn.net/download/weixin_42104154/16486720).

pdf版下载
------

pdf下载链接已经放在文末，大家可以点链接下载，个人总结，仅供学习参考，勿商用  
[https://download.csdn.net/download/weixin_42104154/85783343](https://download.csdn.net/download/weixin_42104154/85783343)