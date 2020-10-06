[中文](./README.md) [English](./README_en.md)
## nanoCH55x 开发板
CH55x 系列芯片是南京沁恒微电子股份有限公司推出的8051内核的单片机，包括CH551、CH552、CH554、CH559，nanoCH55x是实验室基于CH552制作的开发板，支持最高24MHz 系统主频，内置16K 程序存储器ROM 和256 字节内部iRAM 以及1K 字节片内xRAM，xRAM 支持DMA直接内存存取。
CH552内置了ADC 模数转换、触摸按键电容检测、3 组定时器和信号捕捉及PWM、双异步串口、SPI、USB设备控制器和全速收发器、USB type-C等功能模块。  
![board-top](https://github.com/wuxx/nanoCH55x/blob/master/doc/board-top.png)

### 烧录说明
- 安装位于software目录下的烧录工具WCHISPTool_Setup.exe  
![wchisptool](https://github.com/wuxx/nanoCH55x/blob/master/doc/wchisptool.png)
- 按住开发板上的按键，插入PC USB口中  
- 选择CH55x标签页，选择需要烧录的固件文件，点击下载即可烧录  
![how-to-flash](https://github.com/wuxx/nanoCH55x/blob/master/doc/how-to-flash.png)

### 注意事项
1. 51系列单片机的栈极小，对于CH552，栈仅有128Bytes，所以在编程时务必注意控制函数调用的层次以及局部变量的定义，一旦栈溢出，将发生程序崩溃或者其他不可预知的后果。

1. 从官方发布的手册来看，CH552的ROM由于使用了iFlash工艺，在5V电源下仅能进行约200次的编程：可以说相当之少了，这应该是沁恒设计时考虑成本和功能之间的权衡，在实际产品中一般仅需要对芯片进行一次编程即可出厂，后续也极少需要升级。不过这个次数是厂商给的较为保守的值，实际测试不止200次，然而在作为开发板使用时仍需注意，推荐一次制作或者购买多块开发板进行开发测试。


### 参考资料
- http://club.szlcsc.com/article/details_9799_1.html
- https://bbs.21ic.com/icview-2537566-1-1.html?ordertype=2
- http://www.wch.cn/products/CH552.html
