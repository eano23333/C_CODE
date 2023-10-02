* 变量：当全局和局部变量名字相同，优先局部

* scanf：在vs中使用scanf时需要宏定义

  ```c
  #define _CRT_SECURE_NO_WARNINGS
  ```

  

* ```c
  extern int a;	//声明一个外部文件中定义的变量
  ```

* ```c
  const int //常变量（不可改的变量）
  ```

* ```c
  //枚举常量
  enum Color
  {
  	RED,
  	YELLOW,
  	BLUE
  };
  //使用时：
  int main()
  {
  	enum Color c = RED;
      
      return 0;
  }		
  ```

* 字符串

  ```c
  //字符串的结束标志为\0
  char arr1[]="abc"
  char arr2[]={'a','b','c','\0'}
  //以上两行才是等效的
  ```

* strlen 函数

  ```c
  #include <string.h>
  //需要include该头文件
  ```

* 打印类型

  ```c
  %d	整型
  %c	字符
  %S	字符串
  %f	float类型
  %lf	double类型
  %zu	size of的返回值
  ```

* 转义字符

  ```c
  \r 回车
  \t 水平制表符
  \v 垂直制表符
  \ddd ddd为1~3位八进制数
  \xdd dd为2位十六进制数
  ```

  eg:![image-20231002014720964](C:\Users\93415\AppData\Roaming\Typora\typora-user-images\image-20231002014720964.png)

​		输出结果：14

* 