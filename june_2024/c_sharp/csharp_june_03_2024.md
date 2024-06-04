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


### GPT 4o问答
1. Q: <div style="background-color: #231200"> 为什么在任何 C# 程序中的第一条语句都是：using System; </div>

    A: <div style="background-color: #2A0130">在 C# 程序中的第一条语句通常是 using System;，其原因如下：

    1. 引入命名空间：using System; 语句用于引入 System 命名空间。System命名空间包含了许多基础类和方法，这些类和方法是 C# 程序常用的。例如Console 类用于控制台输入和输出，Math 类用于数学运算等。
    2. 简化代码书写：通过引入 System 命名空间，可以避免在代码中重复写出整的类名。例如，引入 System 命名空间后，可以直接使用 ConsoleWriteLine，而无需写成 System.Console.WriteLine。
    3. 提高代码可读性：使用 using 语句引入命名空间可以使代码更加简洁和读，减少冗余的命名空间前缀，使代码结构更清晰。</div>


2. Q: <div style="background-color: #231200"> using System 会不会造成引用了过多的内容的情况？
    类似于c++ 的using namespace的情况 </div>

    A: <div style="background-color: #2A0130">在 C# 中，using System; 和 C++ 中的 using namespace std; 有一些相似之处，但也有显著的区别。

    相似之处
    1. 简化代码书写：两者都能让代码书写更加简洁，不需要每次使用类型时都写出完全限定名。
    2. 引入命名空间：两者都是引入一个命名空间，从而使命名空间内的类型可以直接使用。

    不同之处
    1. 作用范围：在 C++ 中，using namespace std; 会将整个标准库命名空间引入到当前作用域，可能会导致命名冲突，特别是在大型项目中。而在 C# 中，using System; 引入的 System 命名空间通常不会引起同样的命名冲突问题，因为 C# 的命名空间设计和库设计更加规范。

    2. 编译和性能：在 C# 中，using 语句仅在编译时起作用，不会在运行时引入不必要的开销。编译器只会在使用到的类型上生成代码，而不会因为 using 语句的存在而生成额外的代码。相比之下，C++ 的 using namespace 可能在某些情况下引入命名冲突和可维护性问题。

    3. 命名冲突处理：C# 具有更好的命名冲突处理机制。如果在 C# 中引入的命名空间发生冲突，可以通过使用别名或显式的命名空间来解决，而在 C++ 中，这种情况可能需要更多的手动干预。
    
    以下是 C# 代码示例，展示了使用 using System; 和可能的命名冲突解决方案：
    </div>

    ```csharp
    using System;
    using System.IO; // 另一个常用的命名空间

    class Program
    {
        static void Main()
        {
            Console.WriteLine("Hello, world!");
            
            // 使用完全限定名来避免冲突
            System.Console.WriteLine("Using fully qualified name to avoid conflict.");
        }
    }
    ```

4. <div style="background-color: #2A0130">
    在这个例子中，即使引入了多个命名空间，C# 也能很好地处理命名冲突。而且 using System; 不会导致运行时的额外开销。

    **总结**
    在 C# 中，using System; 并不会导致像 C++ 中 using namespace std; 那样的问题。它不会在运行时引入多余的内容，也不容易导致命名冲突。C# 的命名空间管理机制和编译器优化使得使用 using 语句是一种安全且高效的实践。
    </div>
