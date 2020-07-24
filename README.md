# pool based dex对比

balancer变量说明：
* n: token数量
* w: 资产价值比重, 小于1。balancer share pool配置参数，不可修改。
* p: n1/n2 * (w2/w1)
* v: n1^w1 * n2^w2

curve变量及公式说明
* n1: swap前token1的数量
* n2: swap前token2的数量
* n1': swap后token1的数量
* n2': swap后token2的数量
* swap前后token1，token2的数量满足： 


|  item \ project  |  uniswap                   | balancer                        |  curve                   |
|  ---             |  ---                       |  ---                            |  ---                     |
| 添加流动性 前后对比 |  n1/n2 值不变               |  p不变, v变大, w不变              |  池子中仅添加的token的数量增加，其他不变   |
| 减少流动性 前后对比 |  n1/n2 值不变               |  p不变, v变小, w不变              |  池子中仅减少流动性的token数量减少，其他不变                        |
| swap 前后对比     |  n1 * n2 值不变             |  p变化(w越大p变化越慢), v不变, w不变 |                          |
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
