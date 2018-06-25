# alculateRunway函数记录
## alculateRunway函数优化前的gas消耗记录
| 添加账号序号 | 优化前gas消耗 |
| ------ | -------- |
| 1      | 1694     |
| 2      | 2475     |
| 3      | 3256     |
| 4      | 4037     |
| 6      | 4818     |
| 5      | 5599     |
| 7      | 6380     |
| 8      | 7161     |
| 9      | 7942     |
| 10     | 8723     |

alculateRunway函数调用的gas的消耗不断增大。因为在alculateRunway函数中进行了员工的数组的遍历累计，当员工数量增加的时候，每遍历一次所需的计算步骤增多，消耗的gas会变大。所以拟用状态变量totalSalary专门记录当前所有员工的薪水合计的值，这样就不用每次都进行遍历计算了。然后在添加、更新、删除员工数据的时候，修改totalSalary变量的值，在alculateRunway中只需要直接调用这个状态变量就可以了。

## alculateRunway函数优化后的gas消耗记录
| 添加账号序号 | 优化后gas消耗 |
| ------ | -------- |
| 1      | 860      |
| 2      | 860      |
| 3      | 860      |
| 4      | 860      |
| 5      | 860      |