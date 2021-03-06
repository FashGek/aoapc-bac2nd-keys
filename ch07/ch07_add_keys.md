
[TOC]



# 补充题解 - 《经典》- 第 7 章 暴力求解法

## 习题 7-17 　Gokigen Naname 谜题（ Gokigen Naname, UVa11694）

首先考虑建模，将每个交叉点看做图的一个结点，所有的斜线就是边。根据每个交叉点上的数字其实都是一种线索。采用类似于玩数独游戏思路，对于结点v(i,j)，记其上标记的数字为d, 周围方块中还未填上斜线的格子数目为f，已经填上和v连接的斜线的格子数目为c。分别考虑以下情况：

1. c = d且f > 0，说明v的连接数目已经满足并且周围还有空的格子。需要将空的格子中全部填成不与v连接的斜线。
2. c + f = d，说明剩下的空格子需要全部填成与v连接的斜线。

不停的轮询所有v，满足以上条件的就进行填充。当没有可以填充的v并且还剩下格子未填充时。就需要采用回溯法，对每个格子的斜线方向进行决策，在任何格子填入斜线连接两个v之前要判断其连通性，如果已经连通则不能填入。

本题实现代码细节较多，请参考代码。













