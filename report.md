## 指令的处理

首先通过文件读入，认为每一行有一个指令。用一个结构体来表示指令，opt表示指令类型，arg1~arg6为6个参数。

opt值对应的指令为，Move为1，Split为2，Merge为3，Input为4，Output为5，而Mix拆分为若干Move进行处理。

具体参数如下：

```
Move(op==1):   x1,y1,x2,y2       (从1移动至2)
Split(op==2):  x1,y1,x2,y2,x3,y3 (由1分成2、3)
Merge(op==3):  x1,y1,x2,y2       (将1、2合并到中间位置)
Input(op==4):  x1,y1             (输入到1位置)
Output(op==5): x1,y1             (由1位置输出)
```