字符型
=======

.. csv-table::
	:header: 类型关键字, 类型说明, 存储大小(linux), 值范围, 示例
	:widths: 15, 20, 20, 20, 30

	char, 有符号字符型, sizeof(short)=1[x86和x86_64], -128~127, char a = 'a'/0x61
	unsigned char, 无符号字符型, sizeof(unsigned short)=1[x86和x86_64], 0~255, unsigned char a = 0xff

在C中我们可以将\ ``char``\ 和\ ``unsigned char``\ 理解成\ ``1 Bytes的整型数``\ ===对照\ ``ASCII码表``\ 

- \ ``char a = 'a'``\ 、\ ``char a = 0x61``\ 、\ ``int a = 97``\ 三者是等价的

\ **注意**\ 

- \ ``'a'``\ ：单引号表示字符
- \ ``"a"``\ ：双引号表示字符串

