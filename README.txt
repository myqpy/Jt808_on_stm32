/*********************************************************************************************/
本文档使用 TAB = 4 对齐，使用keil5默认配置打开阅读比较方便。
【*】程序简介

-工程名称：JT808_ON_STM32
-MDK版本：5.16
-ST固件库版本：3.5.0

【 ！】功能简介：
本程序适用于STM32F103开发板对GPS模块传输回的数据进行解码后通过4G模块使用JT-808协议对位置数据进行上传。

【 ！】实验操作：
1.把GPS模块和4G模块按下面引脚分配说明与开发板连接好
2.给开发板烧录本程序
3.使用串口调试助手可接收开发板返回的调试信息，串口配置为：115200-N-1，

【*】注意事项：
在初次使用GPS模块时，由于没有记录信息，GPS模块需要花费较长时间来搜索卫星，
搜索时间受信号影响，如果不使用有源天线，请尽量在室外测试。
如果使用有源天线的话，接上后，把天线放到窗外即可很快搜索到卫星。

/*******************************************************************************************************************/

【*】 引脚分配


串口(TTL-USB TO USART)：
CH340的收发引脚与STM32的发收引脚相连。
	RX<--->PA9
	TX<--->PA10

移远EC20 4G模块
STM32开发板  <---->  GPS模块

        GND  <---->  GND
        3.3V <---->  VCC
        PA2 <---->  RXD
        PA3 <---->  TXD


GPS模块：
STM32开发板  <---->  GPS模块

        GND  <---->  GND
        3.3V <---->  VCC
        PB10 <---->  RXD
        PB11 <---->  TXD
        
STM32的相关引脚可在板子引出的usart排针组处找到。
-----------------------------------

SDIO(microSD卡座，支持32G以内的SD卡)：
microtSD卡座的SDIO接口与STM32的SDIO相连。
		SDIO_D0	<--->PC8
		SDIO_D1	<--->PC9
		SDIO_D2	<--->PC10
		SDIO_D3	<--->PC11
		SDIO_CK	<--->PC12
		SDIO_CMD<--->PD2

												
/*****************************************************************************************************/

/*********************************************************************************************/

【*】 版本

-程序版本：1.0
-发布日期：2023-01

-版本更新说明：首次发布
