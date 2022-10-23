> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/m0_60718520/article/details/127455913?spm=1000.2115.3001.6382&utm_medium=distribute.pc_feed_v2.none-task-blog-hot_rank_bottoming-2-127455913-null-null.pc_personrec&depth_1-utm_source=distribute.pc_feed_v2.none-task-blog-hot_rank_bottoming-2-127455913-null-null.pc_personrec)

前言： I2C主要在服务应用在管理系统的配置或掌握组件的功能状态，如电源和系统风扇。可随时监控内存、硬盘、网络、系统温度等多个参数，增加了系统的安全性，方便了管理。

**目录**

[一、I2C总线通信原理](#t0)

[1、I2C总线简介](#t1)

[2、I2C总线物理·拓扑结构](#t2)

[3、I2C协议规定的开始信号、结束信号和应答信号](#t3)

[4、数据传输](#t4)

[5、STM32F4-I2C控制器特性](#t5)

[6、框图](#t6)

[二、EEPROM（24CXX）存储芯片介绍](#t7)

[1、EEPRROM简介](#t8)

[2、本芯片AT24C02芯片简介](#t9)

[（1）设备地址](#t10)

[（2） 硬件和原理图](#t11)

[（3）读写时序（根据AT24C02芯片手册内容）](#t12)

[三、2IC读写EEPROM实例HAL库版本](#t13)

[1、实验要求：实现主机与EEPROM（24C02）双向通信。](#t14)

[2、硬件原理图分析](#t15)

[3、cubmx配置](#t16)

[4、编程思路](#t17)

[5、实验效果](#t18)

[四、2IC读写EEPROM实例软件模拟设计](#t19)

* * *

一、I2C总线通信原理
===========

1、I2C总线简介
---------

I2C（Inter-Integrated Circuit）总线（也称IIC或I2C）是由PHILIPS公司开发的两线式串行总线，用于连接微控制器及其外围设备，是微电子通信控制领域广泛采用的一种总线标准。它是**同步通信**的一种特殊形式，具有接口线少，控制方式简单，期间封装形式少，通信速率高等优点。

**I2C总线特征**

*   两条总线线路：**一条串行数据SDA，一条串行时钟线SCL来**完成数据的传输及外围器件的扩展
*   I2C总线上的**每一个设备都可以作为主设备或者从设备，而且每一个设备都会对应一个唯一的地址**
*   I2C总线数据传输速率在标准模式下可达100kbit/s，快速模式下可达400kbit/s，高速模式下可达3.4Mbit/s。一般通过I2C总线接口可编程时钟来实现传输速率的调整，同时也跟所接的上拉电阻的阻值有关。
*   I2C总线上的主设备与从设备之间以字节**(8位)**为单位进行**单双工的数据传输**。

**2、I2C总线物理·拓扑结构**
------------------

![](https://img-blog.csdnimg.cn/9bf34052ffb44f61b889ab05e0e1a2f9.png)  
I2C 总线在物理连接上分别由SDA(串行数据线)和SCL(串行时钟线)及上拉电阻组成。通信原理是通过对SCL和SDA线高低电平时序的控制，来产生I2C总线协议所需要的信号进行数据的传递。**在总线空闲状态时，这两根线一般被上面所接的上拉电阻拉高，保持着高电平。**

**3、I2C协议规定的**开始信号、结束信号和应答信号
----------------------------

总线上数据的传输必须以一个起始信号作为开始条件，以一个结束信号作为传输的停止条件。起始和结束信号总是由主设备产生。

I2C 总线在传送数据过程中共有三种类型信号， 它们分别是：开始信号、结束信号和应答信号。

*   开始信号：**SCL 为高电平时，SDA 由高电平向低电平跳变，开始传送数据。**
*   结束信号：**SCL 为高电平时，SDA 由低电平向高电平跳变，结束传送数据。**
*   应答信号：接收数据的 IC 在接收到 8bit 数据后，向发送数据的 IC 发出特定的低电平脉冲，表示已收到数据。CPU 向受控单元发出一个信号后，等待受控单元发出一个应答信号，CPU 接收到应答信号后，根据实际情况作出是否继续传递信号的判断。若未收到应答信号，由判断为受控单元出现故障。这些信号中，**起始信号是必需的，结束信号和应答信号，都可以不要。**

![](https://img-blog.csdnimg.cn/81103d70ca1c4f6895f2edb0106cb8e7.png)

4、数据传输
------

数据传输以 字节为单位 , 主设备在SCL线上产生每个时钟脉冲的过程中将在SDA线上传输一个数据位， 数据在时钟的高电平被采样，一个字节按数据位 **从高位到低位**的顺序进行传输。 主设备在传输有效数据之前 要 先指定从设备的地址，一般为7位，然后再发生数据传输的方向位， 0表示主设备向从设备写数据，1表示主设备向从设备读数据。 应答信号 **接收数据的器件** 在接收到 8bit 数据后，向发送数据的器件发出 **低电平** 的应答信号，表示已收到数据。这个信号可以是主控器件发出，也可以是从动器件发出。总之，由接收数据的器件发出。  **非应答数据线拉高来表示**。

![](https://img-blog.csdnimg.cn/18c1c1be7008465aacf165b5e095fd1d.png)

*    主设备往从设备写数据 （W0）

![](https://img-blog.csdnimg.cn/845cc32dbe374e359f26da633ba3bde5.png)

*     主设备读从设备数据 （R1）

![](https://img-blog.csdnimg.cn/b8e05c2ad5d84bd5b28b35a651ccac60.png)

5、STM32F4-I2C控制器特性
------------------

**软件模拟I2C时序**  
由于直接控制 GPIO 引脚电平产生通讯时序时，需要由 CPU 控制每个时刻的引脚状态，所以称之为“软件模拟协议”方式。

**硬件控制产生I2C时序**  
STM32 的 I2C 片上外设专门负责实现 I2C 通讯协议，只要配置好该外设，它就会自动根据协议要求产生通讯信号，收发数据并缓存起来，CPU只要检测该外设的状态和访问数据寄存器，就能完成数据收发。这种由**硬件外设处理 I2C协议的方式减轻了 CPU 的工作，且使软件设计更加简单**。

6、框图
----

![](https://img-blog.csdnimg.cn/cf7bdc18523240639c3041e3673a5527.png)

I2C的主要特点  
● I2C总线规范 rev03 兼容性：  
－ 从机模式和主机模式  
－ 多主机功能－ 标准模式（高达 100kHz ）  
－ 快速模式（高达 400kHz ）  
－ 超快速模式（高达 1 MHz ）  
－ 7 位和 10 位地址模式  
－ 软件复位  
● 1 字节缓冲带 DMA 功能

STM32F4-I2C通讯引脚：STM32芯片有多个I2C外设，它们的I2C通讯信号引出到不同的GPIO引脚上，使用时必须配置到这些指定的引脚。

![](https://img-blog.csdnimg.cn/8b9842b7ec8c4f3db1691f67820672aa.png)

二、EEPROM（24CXX）存储芯片介绍
=====================

**1、EEPRROM简介**
---------------

EEPROM (Electrically Erasable Programmable read only memory)，带电可擦可编程只读存储器--一种掉电后数据不丢失的存储芯片。 EEPROM 可以在电脑上或专用设备上擦除已有信息，重新编程。         
**EEPROM常用来存储一些配置信息，以便系统重新上电的时候加载之**。EEPOM 芯片最常用的通讯方式就是 I 2 C 协议  
AT24XX芯片容量    XX表示：01、02、04、16、32、64、…..    单位： Kbit

**2、本芯片AT24C02芯片简介**
--------------------

AT24C02是一个2K位串行CMOS，内部含有256个字节，此芯片具有I2C通讯接口，芯片内保存的数据在掉电的情况下不丢失（EEPROM），常用于存放比较重要的数据。本实验使用的是SOP-8封装的AT24C02芯片，其引脚说明见下图

![](https://img-blog.csdnimg.cn/dd90b3383a6141d2b001db660bacbc80.png)

![](https://img-blog.csdnimg.cn/3b14e0eab7a8448c8a93ccee1985a5d1.png)![](https://img-blog.csdnimg.cn/fe1e33408d124201ac5898c2eb492c19.png)

### （1）设备地址

24CXX的设备地址：         
24CXX的设备地址为7位：![](https://img-blog.csdnimg.cn/042478e46d0d40318b5b444a03c7a7ef.png)        
高4位恒定为 1010        
低3位取决于A0-A2的电平状态  
注：一般主机在读写24CXX都是把设备地址连同读写位组合成一个字节一起发送

### （2） 硬件和原理图

 ![](https://img-blog.csdnimg.cn/1d893f79d00a4f758bf1e4077c1e0b72.png)

### （3）读写时序（根据AT24C02芯片手册内容）

一个写操作需要8位数据字的地址，跟随着设备地址和响应位。一旦收到地址，EEPROM会再次响应0，然后输入第一个8位数据字。在接收到8位数据字后，EEPROM将输出一个“0”，寻址设备(如微控制器)必须以停止条件终止写序列。

![](https://img-blog.csdnimg.cn/c5e2a9086bdb45e982e9fdbe500463dc.png)

随机读需要一个“空”字节写序列来加载数据字地址。一旦设备地址字和数据字地址被输入并被EEPROM确认，微控制器必须生成另一个启动条件。微控制器通过发送一个设备地址和读写标志位选择1，来启动当前地址的读取。EEPROM确认设备地址并串行输出数据字。 微控制器不响应“0”，但会产生停止条件

![](https://img-blog.csdnimg.cn/54a64eb2f5954d65a5735767cacc91a6.png)

 AT24C02芯片的器件地址为7位，高4位固定为1010，低3位有上表中的A0/A1/A2引脚的电平决定，还有一位（最低位R/W）用来选择读写方向。本实验中A0/A1/A2引脚接在GND上了，因此器件地址为1010000；加上最低位的读写方向位后，写器件地址为**10100000（0xA0），读器件地址为10100001（0xA1）**

SCL:串行时钟，SDA:串行数据I/O

![](https://img-blog.csdnimg.cn/f991bdd602ee4c8f8c15751372650786.png)

 ![](https://img-blog.csdnimg.cn/6b2f1f8f8782412eae5f34e008e094d6.png)

三、2IC读写EEPROM实例HAL库版本
=====================

1、实验要求：实现主机与EEPROM（24C02）双向通信。
------------------------------

2、硬件原理图分析
---------

![](https://img-blog.csdnimg.cn/87effbfbf7b24e35b55cf7f54fd7c4a0.png)

 ![](https://img-blog.csdnimg.cn/cf7ef1fb56d745afbc8d8a1557fb1ea7.png)

IIC的时钟线和数据线对应PB8、PB9

3、cubmx配置
---------

开始168mhz时钟，串口通信，IIC外部管脚配置

![](https://img-blog.csdnimg.cn/0002d87f2d304f9e8580915af011126e.png)

![](https://img-blog.csdnimg.cn/29dc8a6843434c33b48f9116fe1a4239.png)

 ![](https://img-blog.csdnimg.cn/372e17ca40a543188be6e7dcb32962a8.png)

![](https://img-blog.csdnimg.cn/cb9802c961a14b31bfbaf190d6263f47.png)

![](https://img-blog.csdnimg.cn/b8493a117b674f13aa9875942ce25b85.png)

主从地址必须在0到127之间，我们这边只有一个设备所以是0。生产工程打开keil。

4、编程思路
------

实现一个写函数、一个读函数，在主程序中写入EEPROM并从EEPROMN读出来打印

我们使用到两个HAL库函数 

![](https://img-blog.csdnimg.cn/f03c4374508c426c834317795cb2361b.png)

代码中注意我们的EEPROM是8字节使用I2C_MEMADD_SIZE_8BIT

```
`

1.  int fputc(int ch,FILE *p)
2.  {
3.  	while(!(USART1->SR & (1<<7)));
4.  	USART1->DR = (uint8_t) ch;
5.  	return ch;
6.  }

8.  #define  WriteAddr 0xA0
9.  #define  ReadAddr  0xA1

11.  uint8_t Wbuf[20] = "EEPROM TEST OK!";
12.  uint8_t Rbuf[20] = {0};

14.  /********* 24c02 写数据函数 *****************
15.    * @brief  
16.    * @param  MemAddr 起始位置
17.    * @param  数据存储区
18.    * @param  数据长度
19.  ********* 24c02 写数据函数 ******************/
20.  void EEPROM_Write(uint16_t MemAddr,uint8_t *Wbuf, uint16_t len)
21.  {
22.  	while(len--)
23.  	{
24.  		while(HAL_I2C_Mem_Write(&hi2c1, WriteAddr, MemAddr, I2C_MEMADD_SIZE_8BIT, Wbuf,1,100) != HAL_OK){};
25.  		MemAddr++;
26.  		Wbuf++;
27.  	}
28.  }

30.  /********* 24c02 读数据函数 *****************
31.    * @brief  
32.    * @param  MemAddr 起始位置
33.    * @param  数据存储区
34.    * @param  数据长度
35.  ********* 24c02 读数据函数 ******************/
36.  void EEPROM_Read(uint16_t MemAddr,uint8_t *Rbuf, uint16_t len)
37.  {
38.  		while(HAL_I2C_Mem_Read(&hi2c1, ReadAddr, MemAddr, I2C_MEMADD_SIZE_8BIT, Rbuf,len,100) != HAL_OK){};
39.  }

42.  /* USER CODE END 0 */

44.  /**
45.    * @brief  The application entry point.
46.    *
47.    * @retval None
48.    */
49.  int main(void)
50.  {
51.    /* USER CODE BEGIN 1 */

53.    /* USER CODE END 1 */

55.    /* MCU Configuration----------------------------------------------------------*/

57.    /* Reset of all peripherals, Initializes the Flash interface and the Systick. */
58.    HAL_Init();

60.    /* USER CODE BEGIN Init */

62.    /* USER CODE END Init */

64.    /* Configure the system clock */
65.    SystemClock_Config();

67.    /* USER CODE BEGIN SysInit */

69.    /* USER CODE END SysInit */

71.    /* Initialize all configured peripherals */
72.    MX_GPIO_Init();
73.    MX_USART1_UART_Init();
74.    MX_I2C1_Init();
75.    /* USER CODE BEGIN 2 */
76.  	printf("II2C test\r\n");
77.  	EEPROM_Write(0,Wbuf,sizeof(Wbuf));
78.  	HAL_Delay(500);
79.  	EEPROM_Read(0,Rbuf,sizeof(Rbuf));
80.  	printf("%s",Rbuf);

82.    /* USER CODE END 2 */

84.    /* Infinite loop */
85.    /* USER CODE BEGIN WHILE */
86.    while (1)
87.    {

89.    /* USER CODE END WHILE */

91.    /* USER CODE BEGIN 3 */

93.    }
94.    /* USER CODE END 3 */

96.  }

`![](https://csdnimg.cn/release/blogv2/dist/pc/img/newCodeMoreWhite.png)
```

5、实验效果
------

![](https://img-blog.csdnimg.cn/7b54847dd1a74d6e869336b6994b8763.png)

四、2IC读写EEPROM实例软件模拟设计
=====================

后续补充