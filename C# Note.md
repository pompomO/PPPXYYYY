#C# Note
> 快捷键       
Ctrl+K+F:对齐所有代码   
Ctrl+K+C:注释选中代码   
Ctrl+K+U:取消注释

>变量：内存中一块用于存储数据的空间   
1Byte=8bit  

占位符：   
 ````
string content  
= string.Format("name:{0},capacity{1}", gunName, ammoCapacity);  
````

标准字符串格式化   
````
Console.WriteLine("金额:{0:c}", 3333);//￥3,333.00 
Console.WriteLine("Number:{0:d2}", 9);//09  
Console.WriteLine("{0:f1}",1.667);//1.7     
Console.WriteLine("{0:p0}",0.5);//50%
````
>\0:空字符  
\r\n:回车换行   
\t:水平制表格(tab)

> .NET程序编译过程:   
>源代码（.cs)→CLS（CommenSpecification）编译→通用中间语言（.exe,.dll)→机器码

>逻辑运算符:&&,||,!  
>快捷运算符:+=,*=,/=,%=

一元运算符
````
Console.WriteLine(num3++);//3,先返回值，然后自增
Console.WriteLine(++num4);//4,先自增，然后返回值
//++的位置只影响当前指令
````
三元运算符
````
数据类型 变量=条件?true对应的值:false对应的值;
int trian1 = 3 < 4 ? 1 : 0;//trian1=1
int trian2 =false ? 1 : 0;//trian2=0
````

Parse转换：string转其他格式
````
int num2 = int.Parse(strNum1);
float flo1 = float.Parse(strNum1);
````
.ToString():其他格式转string 
   
隐式转换/显示转换
````
byte numA = 255;
int numB = numA;//隐式转换，小范围数据自动转大范围
int numC = 255;
byte numD = (byte)numC;//显示转换，大范围数据强制转小范围数据；数据超范围时会丢失精度

byte a = 1;
a = a+1;//报错
a +=1;//√
````

switch条件结构,变量必须是值
```
switch(str1)
{
    case "+":
        Console.WriteLine(num1 + num2);
        break;
    case "*":
        Console.WriteLine(num1 * num2);
        break;
    default: Console.WriteLine("pa");
        break;
}
```

短路逻辑
````
int n1 = 1,n2 = 2;
bool bol1 = n1>n2 && ++n1==2;//n1=1
bool bol2 = n1<n2 || ++n2==3;//n2=2

````

For循环
````
            double thickness = 0.01;
            for (int i = 0; i < 30; i++)
            {
                if (thickness % 2 != 0) continue;
                thickness *= 2;
            }
            Console.WriteLine(thickness);

````

While循环
````
            double height = 100, distance = height;
            int times = 0;
            while (height / 2 > 0.01)
            {
                height *= 0.5;
                distance += 2 * height;
                times++;
            }
            Console.WriteLine(height);
            Console.WriteLine(times);
            Console.WriteLine(distance);
````

随机数
````
Random random=new Random();
int rand = random.next(1,101);//左闭右开
````

do/while循环 Guess a random number
````
            Random random = new Random();
            int rand=random.Next(1,101);
            Console.WriteLine("write a number between 1 and 100");
            int num1=int.Parse(Console.ReadLine());
            int i = 1;
            int judgeNum;
            do
            {
                judgeNum = num1 - rand;
                if (judgeNum > 0)
                {
                    i++;
                    Console.WriteLine("your number is bigger,{0}times:",i);
                    num1 = int.Parse(Console.ReadLine());
                }
                else if (judgeNum < 0)
                {
                    i++;
                    Console.WriteLine("your number is smaller,{0}times:", i);
                    num1 = int.Parse(Console.ReadLine());

                }

                else if (judgeNum==0)
                {
                    Console.WriteLine("right,{0} times in total",i);
                    break;
                }
            } while (true);

````

定义方法  
````  
[访问修饰符] [可选修饰符] 返回类型 方法名称(参数列表)（首字母大写）
{
    方法体
    return 结果;
}
````