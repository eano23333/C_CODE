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

  ![image-20231002204057468](C:\Users\93415\AppData\Roaming\Typora\typora-user-images\image-20231002204057468.png)

* strlen 函数

  ```c
  #include <string.h>
  //需要include该头文件
  ```

* 打印类型

  ```c
  %d	//整型
  %c	//字符
  %S	//字符串
  %f	//float类型
  %lf	//double类型
  %zu	//size of的返回值
  %p	//打印地址(16进制)
  ```

* 转义字符

  ```c
  \r //回车
  \t //水平制表符
  \v //垂直制表符
  \ddd //ddd为1~3位八进制数
  \xdd //dd为2位十六进制数
  ```

  eg:![image-20231002014720964](C:\Users\93415\AppData\Roaming\Typora\typora-user-images\image-20231002014720964.png)

​		输出结果：14

* 数组

  ```c
  定义： arr[常量]
  操作： arr[可以为变量]
  ```

  * c99标准：支持定义变长数组，但不可初始化，即以下代码错误：

    ```c
    int n=1;int arr[n]={0};//错误
    ```

* 关键词 typedef

  ```c
  typedef unsigned int unit;	//对类型重命名
  uint a = 1;
  ```

  

* 关键词 static

  * static修饰局部变量：

  ```c
  //static修饰局部变量时，局部变量出了作用域也不会销毁
  //局部变量的性质不改变，不会因此变成全局变量
  #include <stdio.h>
   void test()
   {
       static int a = 1;	//a每次自增后的值会保留
       a++;
       printf("%d",a);
   }
  int main()
  {
      int i = 0;
      while(i<10)
      {
          test();
          i++;
      }
      return 0;
  }
  
  //打印结果：2~11
  ```

  * static修饰全局变量

  ```c
  //static 修饰全局变量时，外部链接属性失效
  //即不可被其他文件用extern再使用
  ```

  * static修饰函数

    ```c
    //函数也具有外部链接属性，可用extern
    //static修饰函数时，函数的外部链接属性也失效
    ```

    

* 关键词：寄存器变量register

```c
register int a = 1;		//把3存放在寄存器中，读写速度更快
```

* #define		（预处理指令，不是关键词）

  * 定义标识符

    ```c
    #define PI 3.14
    ```

  * 定义宏

    ```c
    #define Add(x,y) x+y	//相当于定义了一个函数
    ```



* 指针

```c
int* p;		//定义单个指针
int *p1,*p2,*p3;	//定义多个指针
```

* 结构体struct

  ```c
  struct Student		//结构体对象
  {
      char name[20];
      int age;
      char gender[10];
      char tele[12];		//成员
  };
  
  int main()
  {
      struct Student a = {"eano",20,"male","15375592688"}
      //结构体对象.成员名
      printf("%s %d %s %s\n",a.name,a.age,a.gender,a.tele);
      return 0;
  }
  ```

  ```c
  void print(struct Student* p)
  {
      printf("%s %d %s %s\n",(*p).name,(*p).age),(*p).gender,(*p).tele);	//(*结构体指针).成员名
      
      printf("%s %d %s %s\n",p->name,p->age,p->gender,p->tele);    //结构体指针变量->成员名
      
      //上述两种写法一致
  }
  ```

  

