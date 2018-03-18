字符串
=======

字符串是内存中一段连续的char空间，以\ ``'\0'``\ 结尾：例如\ ``"a"``\ 表示\ ``'a'``\ 和\ ``'\0'``\ 

注意：\ ``'a'``\ 表示int类型或char类型；\ ``"a"``\ 才表示字符串类型

字符串的定义初始化方法有两种

- 字符char数组
- 字符char指针

.. code-block:: c

	//字符char数组
	/*
	*字符串的长度一定不能超过char数组的长度，因为字符串是以'\0'结尾的，必须保证char数组的最后一个元素的值是'\0'
	*所以在定义char数组时就将其初始化为0
	*/
	char a[10]={‘h’,’e’,’l’,’l’,’o’};//初始化时，元素'o'后面的元素初始化为0即'\0'，所以它也是一段连续的char空间，并以'0'结尾
	char a[10]="hello";              //初始化时，a[0]~a[4]分别被初始化'h'/'e'/'l'/'l'/'o'，剩余元素初始为0
	char a[10]={ 0 };                //初始化时，所有元素都初始为0
	char a[]="hello";                //初始化时，数组a有6个元素a[0]~a[5]，分别为'h'/'e'/'l'/'l'/'o'/'\0'

	//字符char指针
	char *p = "hello";               //定义一个char类型的指针指向字符串

	//char指针可以引用char数组
	char b[10] = "hello";
	char *p = b;


下面有一个demo，实现功能是：去掉给定字符串后面的空格

.. code-block:: c

	#include <stdio.h>
	
	int main(){
		char a[] = "hello world a     ";
		int index=sizeof(a)/sizeof(a[0])-2;//数组a的最后一个元素是字符串结尾的‘0’，所以需要从倒数第二个元素开始遍历的 
		while(a[index]){
			if(a[index] != ' '){
				a[index+1] = 0;
				break;
			} 
			index--;
		}
		printf("%s\n",a);
	}