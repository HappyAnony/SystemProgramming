数值型
========

数值型可分为两大类：

- \ `整型 <#integer>`_\ 
- \ `浮点型 <#float>`_\ 

.. _integer:

0x00 整型
~~~~~~~~~~~~~

.. csv-table::
	:header: 类型关键字, 类型说明, 存储大小(linux), 值范围, 示例
	:widths: 15, 30, 30, 30, 30

	short, 有符号短整型, sizeof(short)=2[x86和x86_64], 	-32768~32767, short a = 20;
	unsigned short, 无符号短整型, sizeof(unsigned short)=2[x86和x86_64], 0~65535, unsigned short a = 20;
	int, 有符号整型, sizeof(int)=2[x86]/4[x86_64], -32768~32767或-2147483648~2147483647, int a = 20[10进制]/020[8进制]/0x20[16进制];
	unsigned int, 无符号整型, sizeof(unsigned int)=2[x86]/4[x86_64], 0~65535或0~4294967295, unsigned int a = 20;
	long, 有符号长整型, sizeof(long)=4[x86]/8[x86_64], -2147483648~2147483647或‭-9223372036854775808‬~‭9223372036854775807‬, long a = 20;
	unsigned long, 无符号长整型, sizeof(unsigned long)=4[x86]/8[x86_64], 0~4294967295或0~‭1777777777777777777777‬, unsigned long a = 20;
	long long, 有符号长长整型, sizeof(long long)=8[x86和x86_64], -9223372036854775808‬~‭9223372036854775807, long long a = 20;
	unsigned long long, 无符号长长整型, sizeof(unsigned long long)=8[x86和x86_64], 0~‭1777777777777777777777, unsigned long long a = 20;‬

.. csv-table::
	:header: 整型数, 对应类型
	:widths: 20, 20

	100, int
	100u, unsigned int
	100l, long
	100ul, unsigned long
	100ll, long long
	100ull, unsigned long long

整型数据存在两种类型的溢出

- \ **符号位溢出**\ ：超过有符号数的最大值
- \ **最高位溢出**\ ：超过无符号数的最大值

\ **注意**\ ：在所有数值类型中(包括浮点型)，计算机CPU处理int类型数据的效率是最高的，int只是占用较大内存而已


.. _float:

0x01 浮点型
~~~~~~~~~~~~

.. csv-table::
	:header: 类型关键字, 类型说明, 存储大小(linux), 值范围, 精度
	:widths: 15, 20, 20, 15, 10

	float, 单精度浮点数, sizeof(float)=4[x86_64], 	1.2E-38~3.4E+38, 6位小数
	double, 双精度浮点数, sizeof(double)=8[x86_64], 2.3E-308~1.7E+308, 15位小数
	long double, 长双精度浮点数, sizeof(long double)=16[x86_64], 3.4E-4932~1.1E+4932, 18位小数

在头文件\ ``float.h``\ 定义了浮点型相关的宏；通过这些宏可以输出浮点类型占用的存储空间以及它的范围值

.. code-block:: c

	#include <stdio.h>
	#include <float.h>

	int main()
	{
	   printf("Storage size for float : %d \n", sizeof(float));
	   printf("Minimum float positive value: %E\n", FLT_MIN );
	   printf("Maximum float positive value: %E\n", FLT_MAX );
	   printf("Precision value: %d\n", FLT_DIG );
	   
	   return 0;
	}

