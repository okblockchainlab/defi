# pool based dex对比

* n: token数量
* w: 资产价值比重, 小于1。balancer share pool配置参数，不可修改。
* p: n1/n2 * (w2/w1)
* v: n1^w1 * n2^w2

|  item \ project  |  uniswap                   | balancer                        |  curve                   |
|  ---             |  ---                       |  ---                            |  ---                     |
| 添加流动性 前后对比 |  n1/n2 值不变               |  p不变, v变大, w不变              |                          |
| 减少流动性 前后对比 |  n1/n2 值不变               |  p不变, v变小, w不变              |                          |
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
