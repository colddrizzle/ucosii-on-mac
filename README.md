本项目的目的在于将ucos-ii的代码在macos上通过模拟的方式跑起来

因为ucos-ii本质上没有时间片轮转调度策略，需要任务自己放弃CPU，所以任务切换是可预期，可以使用类似函数调用的方式来完成任务切换。

中断的模拟:在不对CPU进行编程的情况下中断时没法进行模拟的，幸运的是单纯ucos-ii运行需要的中断只有两个：任务切换的中断和时钟中断，任务切换可以通过函数调用来模拟掉，而时钟处理可以通过线程来模拟掉。

项目代码来源于https://www.micrium.com/download/ucos-ii-kernel-trial/ version:2.91

环境：macos gcc

需要编写的函数：
ucos_ii.h 1367行所规定的三个函数

数据类型 

宏定义

任务堆栈的初始化函数OSTaskStkInit

具体哪些东西可以参考window与dos的移植版本代码
