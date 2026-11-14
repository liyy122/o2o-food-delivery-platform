# 接口清单

> 由 `sky-server` 中的 Controller 整理而来，与代码保持一致。
> 启动后也可以访问 `http://localhost:8080/doc.html`（Knife4j）在线调试。

## 管理端

### 分类相关接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| POST | `/admin/category` | 新增分类 |
| GET | `/admin/category/page` | 分类分页查询 |
| DELETE | `/admin/category` | 删除分类 |
| PUT | `/admin/category` | 修改分类 |
| POST | `/admin/category/status/{status}` | 启用禁用分类 |
| GET | `/admin/category/list` | 根据类型查询分类 |

### 通用接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| POST | `/admin/common/upload` | 上传文件 |

### 菜品相关接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| POST | `/admin/dish` | 新增菜品 |
| GET | `/admin/dish/page` | 菜品分页查询 |
| DELETE | `/admin/dish` | 批量删除菜品 |
| GET | `/admin/dish/{id}` | 根据id查询菜品 |
| PUT | `/admin/dish` | 修改菜品 |
| POST | `/admin/dish/status/{status}` | 菜品起售停售 |
| GET | `/admin/dish/list` | 根据分类id查询菜品 |

### 员工相关接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| POST | `/admin/employee/login` | 员工登录 |
| POST | `/admin/employee/logout` | 员工退出 |
| POST | `/admin/employee` | 新增员工 |
| GET | `/admin/employee/page` | 分页查询 |
| POST | `/admin/employee/status/{status}` | 启用禁用员工账号 |
| GET | `/admin/employee/{id}` | 根据id查询员工信息 |
| PUT | `/admin/employee` | 编辑员工信息 |

### 订单管理接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| GET | `/admin/order/conditionSearch` | 订单搜索 |
| GET | `/admin/order/statistics` | 各个状态的订单数量统计 |
| GET | `/admin/order/details/{id}` | 查询订单详情 |
| PUT | `/admin/order/confirm` | 接单 |
| PUT | `/admin/order/rejection` | 拒单 |
| PUT | `/admin/order/cancel` | 取消订单 |
| PUT | `/admin/order/delivery/{id}` | 派送订单 |
| PUT | `/admin/order/complete/{id}` | 完成订单 |

### 数据统计相关接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| GET | `/admin/report/turnoverStatistics` | 营业额统计 |
| GET | `/admin/report/userStatistics` | 用户统计 |
| GET | `/admin/report/ordersStatistics` | 订单统计 |
| GET | `/admin/report/top10` | 销量前十统计 |
| GET | `/admin/report/export` | 导出运营数据报表 |

### 套餐相关接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| POST | `/admin/setmeal` | 新增套餐 |
| GET | `/admin/setmeal/page` | 分页查询 |
| DELETE | `/admin/setmeal` | 批量删除套餐 |
| GET | `/admin/setmeal/{id}` | 根据id查询套餐 |
| PUT | `/admin/setmeal` | 修改套餐 |
| POST | `/admin/setmeal/status/{status}` | 套餐起售停售 |

### 店铺相关接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| PUT | `/admin/shop/{status}` | 设置店铺的营业状态 |
| GET | `/admin/shop/status` | 获取店铺的营业状态 |

### 工作台相关接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| GET | `/admin/workspace/businessData` | 工作台今日数据查询 |
| GET | `/admin/workspace/overviewOrders` | 查询订单管理数据 |
| GET | `/admin/workspace/overviewDishes` | 查询菜品总览 |
| GET | `/admin/workspace/overviewSetmeals` | 查询套餐总览 |

## 用户端

### C端地址簿接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| GET | `/user/addressBook/list` | 查询当前登录用户的所有地址信息 |
| POST | `/user/addressBook` | 新增地址 |
| GET | `/user/addressBook/{id}` | 根据id查询地址 |
| PUT | `/user/addressBook` | 根据id修改地址 |
| PUT | `/user/addressBook/default` | 设置默认地址 |
| DELETE | `/user/addressBook` | 根据id删除地址 |
| GET | `/user/addressBook/default` | 查询默认地址 |

### C端-分类接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| GET | `/user/category/list` | 查询分类 |

### C端-菜品浏览接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| GET | `/user/dish/list` | 根据分类id查询菜品 |

### 用户端订单相关接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| POST | `/user/order/submit` | 用户下单 |
| PUT | `/user/order/payment` | 订单支付 |
| GET | `/user/order/historyOrders` | 历史订单查询 |
| GET | `/user/order/orderDetail/{id}` | 查询订单详情 |
| PUT | `/user/order/cancel/{id}` | 取消订单 |
| POST | `/user/order/repetition/{id}` | 再来一单 |
| GET | `/user/order/reminder/{id}` | 客户催单 |

### C端-套餐浏览接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| GET | `/user/setmeal/list` | 根据分类id查询套餐 |
| GET | `/user/setmeal/dish/{id}` | 根据套餐id查询包含的菜品列表 |

### 店铺相关接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| GET | `/user/shop/status` | 获取店铺的营业状态 |

### C端购物车相关接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| POST | `/user/shoppingCart/add` | 添加购物车 |
| POST | `/user/shoppingCart/sub` | 减少购物车中的商品数量 |
| GET | `/user/shoppingCart/list` | 查看购物车 |
| DELETE | `/user/shoppingCart/clean` | 清空购物车 |

### C端用户相关接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| POST | `/user/user/login` | 微信登陆 |

## 支付回调

### 支付回调接口

| 方法 | 路径 | 说明 |
| --- | --- | --- |
| ANY | `/notify/paySuccess` | - |

---

共 **71** 个接口。
