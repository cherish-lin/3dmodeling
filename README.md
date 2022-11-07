# 3dmodeling
这是对该代码的介绍及使用方法

HalfEdge.h:

该程序构建了半边数据结构，包含点、半边、边、环、面、体六个基本体素，分别对应Vertex,HalfEdge,Edge,Loop,Face,Solid。

EulerOperation.h/EulerOperation.cpp:

使用5个基本欧拉操作：

mvfs:构造一个点，一个面，一个体

mev:构造一个新点，并与给定的点相连形成一条边

mef:在给定两个顶点之间形成一条边，并形成一个新面

kemr:删除给定两个顶点之间相连的一条边，并且生成一个内环

kfmrh:删除一个给定面，并且生成一个内环和一个通孔

main.cpp:

该程序的功能是用户构造一个底面，可以包含多个内环，然后输入扫掠方向和扫掠长度，进行扫掠操作进而形成一个三维模型。

本程序的输入格式为首先输入底面中外环的顶点，然后依次输入外环中各个顶点的位置坐标；然后输入一个内环的顶点数目，以及内环中各个顶点的位置坐标，按这样依次输入所有的内环。
最后输入一个0代表底面构造结束，用户需输入扫掠轴的方向和扫掠长度，然后点击回车便可以得到三维模型的真实感图形显示，运用键盘的wasd键可以控制视角的移动。

本程序的输入样例：

样例一：一个三角形，带有一个三角形内环，延z轴负方向扫掠

3

-0.5 -0.5 0

0.5 -0.5 0

0 0.5 0

3

-0.25 -0.25 0

0.25 -0.25 0

0 0.25 0

0

0 0 -1 0.5

结果为model11.png

样例二：一个五边形，带有两个方形内环，两个三角形内环，延z轴负方向扫掠

5

-1 -1 0

1 -1 0

1 0 0

0 1 0

-1 0 0

4

-0.75 -0.75 0

-0.25 -0.75 0

-0.25 -0.25 0

-0.75 -0.25 0

4

0.25 -0.75 0

0.75 -0.75 0

0.75 -0.25 0

0.25 -0.25 0

3

-0.75 0.2 0

-0.25 0.2 0

-0.25 0.7 0

3

0.25 0.2 0

0.75 0.2 0

0.25 0.7 0

0

0 0 -1 0.5

结果为model12.png


