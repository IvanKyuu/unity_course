# c Sharp Learning Note
## c#教程
source: [C# 教程](https://www.runoob.com/csharp/csharp-tutorial.html)
First program in C#:
```csharp
using System;
namespace HelloWorldApplication
{
    class HelloWorld
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
            Console.ReadKey();
        }
    }
}
```

Expect Output:
`Hello World!`

---
## c#简介
来源：[C# 简介](https://www.runoob.com/csharp/csharp-intro.html)
1. 由微软（Microsoft）开发的，
2. 在 .Net 框架开发期间开发的，
3. C# 是专为[公共语言基础结构](https://en.wikipedia.org/wiki/Common_Language_Infrastructure)（Common Language Infrastructure，CLI）设计的。CLI 由可执行代码和运行时环境组成，允许在不同的计算机平台和体系结构上使用各种高级语言。
   
C# 成为一种广泛应用的专业语言的原因：
+ 现代的、通用的编程语言。
+ 面向对象。
+ 面向组件。
+ 容易学习。
+ 结构化语言。
+ 它产生高效率的程序。
+ 它可以在多种计算机平台上编译。
+ .Net 框架的一部分。


下面列出 C# 一些重要的功能：
+ 布尔条件（Boolean Conditions）
+ 自动垃圾回收（Automatic Garbage Collection）
+ 标准库（Standard Library）
+ 组件版本（Assembly Versioning）
+ 属性（Properties）和事件（Events）
+ 委托（Delegates）和事件管理（Events Management）
+ 易于使用的泛型（Generics）
+ 索引器（Indexers）
+ 条件编译（Conditional Compilation）
+ 简单的多线程（Multithreading）
+ LINQ ([Language Integrated Query (LINQ)](https://learn.microsoft.com/en-us/dotnet/csharp/linq/)) 和 Lambda 表达式
    + ```csharp

        // Specify the data source.
        int[] scores = [97, 92, 81, 60];

        // Define the query expression.
        IEnumerable<int> scoreQuery =
            from score in scores
            where score > 80
            select score;

        // Execute the query.
        foreach (var i in scoreQuery)
        {
            Console.Write(i + " ");
        }

        // Output: 97 92 81
      ```

    + 合着可以在code里面写SQL呢...
+ 集成 Windows


.Net 框架（.Net Framework）:[C# 环境](https://www.runoob.com/csharp/csharp-environment-setup.html)

---
## C# 程序结构
来源：[C# 程序结构](https://www.runoob.com/csharp/csharp-program-structure.html)
与 Java 不同的是，文件名可以不同于类的名称。

Terminal based compile steps:
1. 保存文件为 helloworld.cs。
1. 打开命令提示符工具，定位到文件所保存的目录。
1. terminal 中键入 `csc helloworld.cs` 并按下 enter 键来编译代码。
1. 如果代码没有错误，命令提示符会进入下一行，并生成 helloworld.exe 可执行文件。
1. 接下来，键入 `helloworld` 来执行程序。
1. 您将看到 "Hello World" 打印在屏幕上。
