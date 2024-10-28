# Readme
A note about Page Table.

### 从页的序号到页的物理地址的映射

一个文件可以包含很多页，每一个页都有一个序号，从0开始，当把该文件存储在磁盘中时，每一个页都有一个磁盘地址，当把该文件存储在主存中时，每一个页都有一个主存地址。

可以用一张表把每一个页的序号和每一个页的物理地址关联起来，把这个表称为页表。

当需要读取该文件的某一个页的内容的时候，就根据页的序号从页表中查询对应的页的物理地址。

### 字节的物理地址的计算公式

一个页中通常包含2<sup>p</sup>个字节，每一个字节都有一个字节地址，字节地址的数据结构中包含两个字段：
- 该字节所在的页的序号，可以根据页的序号从页表中查询对应的页的物理地址。
- 该字节在该页中的偏移字节数。

字节的物理地址 = 页的物理地址 + 该字节在该页中的偏移字节数

借助页表，Memory Management Unit可以完成从 (页的序号, 偏移字节数) 到字节的物理地址的转换。

### Credits
- Computer Systems: A Programmer's Perspective, Third Edition
