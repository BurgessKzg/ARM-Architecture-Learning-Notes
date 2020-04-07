&emsp;&emsp;所谓嵌入式开发，就是去控制硬件，也就是驱动。

# 1. ARM基础

## 1.1. ARM公司

&emsp;&emsp;ARM公司前身为Acorn计算机公司，主要设计ARM系列RISC处理器内核，授权ARM内核给生产和销售半导体的合作伙伴(ARM公司不生产芯片)。

## 1.2. ARM产品线

&emsp;&emsp;ARM产品线分为三个系列：
> - Cortex-A系列：高端系列，用于手机这类产品；
> - Cortex-R系列：实时系列，多用于汽车电子等产品；
> - Cortex-M系列：低端系列，用于MCU，FPGA等；

## 1.3. 授权厂商

> - Samsung(三星)；
> - Qualcomm(高通)；
> - Nvidia(英伟达) - 显卡；
> - Freescale(飞思卡尔)(NXP恩智浦)；
> - TI(德州仪器)；
> - Marvell(马维尔) - 网卡；

## 1.4. ARM体系架构

- 不同ARM体系采用不同指令集；
- 冯诺依曼(普林斯顿)结构指令和数据混合存储；
- 哈弗结构指令和数据分开存储；

|ARM体系结构|ARMv4|ARMv5|ARMv6|ARMv7|
|:---:|:---:|:---:|:---:|:---:|:---:|
|ARM CPU|arm7|arm9/arm10|arm11|Cortex-A8|
|流水线|3|5/6|8|NC|
|频率(MHz)|80|150/260|335|667|
|MMU|No/Yes|Yes|Yes|Yes|
|结构|冯氏|哈式|哈式|哈式|

## 1.5. ARM系统硬件组成

- CPU = ALU运算器 + 控制器(取指令) + 寄存器(临时存储)；
- FLASH(NOR,NAND)、eMMC、硬盘；
- 内存；

# 2. 搭建开发环境

## 2.1. 安装交叉编译工具链

&emsp;&emsp;针对不同平台安装。

## 2.2. 安装keil(MDK)

&emsp;&emsp;针对MCU编程，可以测试汇编和C语言。

## 2.3. 创建工程

&emsp;&emsp;在keil中创建工程，添加.s汇编文件名。

## 2.4. keil关联到交叉编译工具链

- 分级找到"Use GCC"选项；
- Project
  - Manager
    - Components
      - Folders
        - 勾选Use GCC
- 设置"GUN Tool Prefix"为安装的交叉编译工具链；
- 设置"GUN Tool Folder"为交叉编译链安装目录；

## 2.5. 导入Linker脚本

- 创建合适的.lds链接文件；
- 分级设置：
- Project
  - Options For Target
    - Linker
- 设置Linker Script File为.lds文件；

## 2.6. 最后

- 编译代码
- 调试代码

# 3. ARM工作模式和寄存器

## 3.1. 7种工作模式

> - 用户(usr)：正常 ARM 程序执行状态；
> - 快中断(fiq)：为支持数据传输或通道处理设计；
> - 中断(irq)：用于一般用途的中断处理；
> - 管理(svc)：操作系统保护模式；
> - 中止(abt): 数据或指令预取中止后进入；
> - 系统(sys)：操作系统的特权用户模式；
> - 未定义(und)：执行了一个未定义指令时进入

## 3.2. 37个寄存器

> - 1个PC寄存器
> - 1个CPSR寄存器
> - 5个SPSR寄存器
> - 30个通用寄存器
>   - R0 - R15
>   - R0 - R14通用寄存器；
>   - R15：PC
>   - R14：LR
>   - R13：SP 
>   - R16：CPSR



