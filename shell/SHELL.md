
# What's shell？

**Shell** 是一种命令行解释器。它是用户与操作系统之间的桥梁，负责解析和执行用户输入的命令

# what's terminal?

**Terminal** 是用户与 Shell 进行交互的界面或应用程序。它提供一个文本窗口，用户可以在其中输入命令

# Different between the shell and terminal

* **Shell**：是命令行解释器，负责解析和执行命令
* **Terminal**：是用于与 Shell 交互的窗口或应用程序
* 可以把 **Shell** 比作汽车的机械结构，而 **Terminal** 是驾驶舱。汽车机械结构（Shell）负责实际的操作和处理，而驾驶舱（Terminal）则提供一个接口，让你可以控制机械结构（shell）。

---
# Commands that confuse me

*具体的见man命令*

```  cat

 * NAME
       cat - concatenate files and print on the standard output

 * SYNOPSIS
       cat [OPTION]... [FILE]...

 * DESCRIPTION
       Concatenate FILE(s) to standard output.

       With no FILE, or when FILE is -, read standard input.

```

#### Think

1. 之前刚刚开始学习的时候 对下面两行命令有点困惑，为什么这两个命令有相同的效果？
``` linux
missing:~$ cat hello.txt
hello
missing:~$ cat < hello.txt
hello
```
本人现在回顾笔记时候想到了这个解释, **<** 将hello.txt的内容重定向到了cat的标准输入上
而 `cat` 读取标准输入的数据并显示它，这与直接指定文件名的效果是相同的。
思考来自 这句话With no FILE, or when FILE is -, read standard input. 

---

2. 之前该课程提供讲义的这段话我也看不太懂，为什么出错了 难道是解析的顺序出问题了？

![[Pasted image 20240729134617.png]]

当时刚刚学习不太理解sudo命令的详细内容，只知道是提升用户权限用的。
`sudo` 是用来提升命令的权限，使其以超级用户（root）身份执行，但它只会提升 `sudo` 命令后的程序的权限，而不是所有操作 ，`sudo echo "text" > file` 中的 `echo` 是以 root 权限执行的，但 `>` 操作符是由 shell 执行的，这部分操作不会被 `sudo` 提升以.
>我当前的理解 , Shell 在执行重定向操作（如 `>` 或 `<`）时，是以当前用户的权限来进行文件操作的

使用`tee`命令就可解决改变亮度的操作
下面是tee的一部分命令解释

![[Pasted image 20240729140828.png]]

# The lecture [notes](https://missing-semester-cn.github.io/2020/course-shell/) for this course

### See the handout of [missing-semester](https://missing-semester-cn.github.io/)for more information
