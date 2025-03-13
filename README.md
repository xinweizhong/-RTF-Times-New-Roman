# -RTF-Times-New-Roman
解决SAS输出RTF时设置字体为宋体（SimSun）但是用Word打开显示为“等线”字体

* 富文本格式（Rich Text Format）即RTF格式，又称多文本格式，是由微软公司开发的跨平台文档格式。大多数的文字处理软件都能读取和保存RTF文档。它是一种方便于不同的设备、系统查看的文本和图形文档格式。

* 在临床统计报告编程过程会用到SAS输出RTF文件的情况，在输出RTF文件时有时候会遇到自己明明在proc template style里面设置的字体为为宋体（SimSun）但是用office Word打开显示为“等线”字体的情况（一般出现unicode SAS中），但是在WPS里面打开有可能显示正常；

* 这可能是因为输出的RTF码中并没有定义宋体（SimSun）这个字体，至于为啥输出的RTF中未定义宋体（SimSun）的原因暂未知，可能是SAS的bug或对多字节兼容性不好造成的。

* 如何解决这个问题呢？

* 我这里提供的思路就是用SAS读取RTF文件并修改RTF码，直接把字体1和字体2分别修改为 宋体（SimSun）和新罗马（Times New Roman），并将每个字的字体修改为新罗马（Times New Roman）代替字体为 宋体（SimSun），然后再输出RTF文件；具体代码实现我写成了一个macro中供大家参考。
