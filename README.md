# pool based dex对比

### balancer变量及公式说明：
* n: token数量
* w: 资产价值比重, 小于1。balancer share pool配置参数，不可修改。
* p: n1/n2 * (w2/w1)
* v: n1^w1 * n2^w2

### curve变量及公式说明
* n1: swap前token1的数量
* n2: swap前token2的数量
* n1': swap后token1的数量
* n2': swap后token2的数量
* swap前后token1，token2的数量满足（其中A是放大系数一个常量，tokens比例不同的池子A不同）： ![](https://github.com/xiangjianmeng/defi/blob/patch-1/img/curve.jpeg)
* 下图中的蓝线即池子token1和token2的swap变化关系：

![](https://github.com/xiangjianmeng/defi/blob/patch-1/img/stableswap.jpeg)
1. curve假设稳定币从价值层面都是锚定1美元的，所以当token1, token2两个稳定币在池子中的比例相近的时候，基本满足1：1swap即1个token会兑换处1个token
2. 当两个稳定币的比例相差较大的时候就会按照Uniswap的兑换规律进行swap，如果池子中20%token1和80%token2，那么在用1个token1能兑换出m个token2来，m>1。比例相差越大，m变化越大即滑点越大。

### defi头部AMM(Automated Market Maker) Dex对比

|  item \ project  |  uniswap                   | balancer                        |  curve                   |
|  ---             |  ---                       |  ---                            |  ---                     |
| 添加流动性 前后对比 |  n1/n2 值不变               |  p不变, v变大, w不变              |  池子中仅添加的token的数量增加，其他不变   |
| 减少流动性 前后对比 |  n1/n2 值不变               |  p不变, v变小, w不变              |  池子中仅减少流动性的token数量减少，其他不变                        |
| swap 前后对比     |  n1 * n2 值不变             |  p变化(w越大p变化越慢), v不变, w不变 | 满足上述图中公式                         |
|                 |                             |                              |                          |
|                 |                             |                              |                          |
|                 |                             |                              |                          |
|                 |                             |                              |                          |
|                 |                             |                              |                          |
|                 |                             |                              |                          |
|                 |                             |                              |                          |
|                 |                             |                              |                          |
|                 |                             |                              |                          |
|                 |                             |                              |                          |
|                 |                             |                              |                          |
|                 |                             |                              |                          |
