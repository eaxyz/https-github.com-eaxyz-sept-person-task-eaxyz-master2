# 1. 阅读和理解样例代码
## 1.1在本地开发环境运行样例工程
![image](https://user-images.githubusercontent.com/86555428/147737280-14cec6f7-decd-41fd-82fc-364dfccc5fe2.png)
***
## 1.2代码结构及部件组成：
系统分为五个类：\
**CommandWords:**\
CommandWords类中，将系统的有效命令定义在字符数组validCommands中，通过方法isCommand(String )判断系统输入的命令是否为有效命令。通过showAll向用户提示系统所有有效命令。\
**Parser：**\
Parser类是一个语法分析器，在此类中通过返回类型为Command的方法getCommand()，对从键盘上输入的语句进行解析。将输入的命令分为word1、word2两部分，调用CommandWords类中方法isCommand来处理word1来判断用户输入的是否为有效命令，从而选择创建不同的Command对象。\
**Command：**\
Command类将接受到的命令进行分离，分离为commandWord、secondWord两部分。同时通过方法isUnknow()判断命令是否有效，通过方法hasSecondWord()判断用户是否输入了后半部分命令。\
**Room:**\
Room类是房间类，代表了游戏中一个位置，房间与房间之间是由出口Exit来连接起来的，玩家可以通过出口来从一个房间到另一个房间。\
**Game:**\
Game类是游戏的主类，Game类的实例将创建并初始化所有其他类:通过方法createrRooms()创建房间，并将它们连接成迷宫；定义了系统有效命令的具体执行方法；创建解析器processCommand(Command)接收用户输入，并将用户输入转换成命令，根据命令调用命令的具体执行方法进行游戏。\
游戏的流程为：系统初始化游戏——接受用户输入的命令——解析器对用户输入进行解析——根据解析结果执行对应方法——向用户展示操作结果
***
## 1.2系统UML图：
![image](https://user-images.githubusercontent.com/86555428/147749311-29261e91-41f1-45ba-9bf4-ffdf0713c97f.png)
***
