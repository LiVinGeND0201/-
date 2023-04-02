# CallBack机制
  callback函数机制通常用于异步编程中。在异步编程中，某些操作可能需要等待一段时间才能完成（例如从网络上下载大量数据）。在等待操作完成的同时，我们可以继续执行其他代码，以避免程序被阻塞。当操作完成后，我们可以使用callback函数机制来通知程序，以便程序可以在操作完成后执行相应的代码。该代码中的callback是通过指针函数实现的，是将函数作为参数传递给其他函数的方式。
# lab5.2具体功能
## linktableInternal.h
  定义了LinkTable的内部数据结构。包括LinkTableNode结构体和LinkTable结构体，这两个结构体分别表示链表的节点和链表本身。这个文件主要被linktable.h和linktable.c引用，提供了链表操作所需的基本数据结构。
  
## linktable.h
这个头文件定义和声明了LinkTable操作的接口。包括创建、删除链表，以及添加、删除、搜索链表节点等功能。同时，这个文件还包含了一些宏定义，例如SUCCESS和FAILURE，用于表示操作结果。
![1](https://user-images.githubusercontent.com/66406371/229354302-da74b5ee-8ec2-45f0-b5ea-3258bbf66206.png)


##linktable.c
  实现了linktable.h中定义的链表操作接口。包括创建链表、删除链表、添加节点、删除节点、搜索节点等功能。这个文件中的函数实现了回调函数机制。例如，SearchLinkTableNode函数通过传入一个回调函数Condition来对链表进行搜索，实现了搜索功能的解耦。
  ![2](https://user-images.githubusercontent.com/66406371/229354308-62965962-f78a-4aff-909b-da470ed3c9e1.png)

## menu.c
  包含了一个简单的命令行菜单程序，它使用了linktable.h提供的链表接口。在这个程序中，命令及其对应的描述和处理函数被存储在一个链表中。程序通过查找链表来处理用户输入的命令。这个程序中的FindCmd函数使用了之前提到的SearchLinkTableNode函数，展示了如何利用回调函数进行搜索。
![3](https://user-images.githubusercontent.com/66406371/229354313-2c7d38b2-43c9-44ac-a810-fb186cbbbb9f.png)
