# 买为

#### 介绍
一个仿淘宝的鸿蒙 HAP，使用 js 开发

#### 买为后端仓库链接
https://gitee.com/HRui66/buy-it-backend

#### 软件架构

#### 消息数据组成设计
##### 用户-用户
|       | send_type    | sender | receiver | content |
|-------|--------------|--------|----------|---------|
| 字符串消息 | int NORMAL=1 | int    | int      | String  |
| 商品分享  | int SHARE=2  | int    | int      | json    |

##### 后台-用户
|              | error_type |
|--------------|------------|
| 消息被对方屏蔽 | int REJECT=3  |
| 对方不接收商品分享  | int REJECT_PRODUCT=4 |


#### 数据库表
  商品表
| 数据项   | 类型             | 长度  | 备注      |
|-------|----------------|-----|---------|
| 商品id  | int            |     | 主键      |
| 商品分类  | vachar         | 10  | 唯一      |
| 商品名   | varchar        | 50  |         |
| 价格    | decimal(20, 2) |     |         |
| 库存| int |     |         |
| 商品主图  | varchar        | 200 |         |
| 商品图id | int            |     | 与商品图表关联 |
| 商家   | int            |     | business|
| 购买人   | int            |     | user    |
| 发布时间  | datetime       |     |         |
| 购买时间  | datetime       |      | |
|状态    |    varchar    |    5    |    |
|介绍    |    text |     |        |

商家表   
| 数据项  | 类型      | 长度 | 备注 |
|------|---------|----|----|
| 商家id | int     |    | 主键 |
| 商家名  | varchar | 10 |    |
| 账号   | int     |    |    |
| 密码   | varchar | 15 |    |


  用户表
| 数据项  | 类型       | 长度  | 备注 |
|------|----------|-----|----|
| 用户id | int      |     | 主键 |
| 用户名  | varchar  | 50  |    |
| 账号   | int      |     | 唯一 |
| 密码   | varchar  | 15  |    |
| 联系方式 | varchar  | 11  |    |
| 邮箱   | varchar  | 20  |    |
| 头像   | varchar  | 250 |    |
| 创建时间 | detetime |     |    |
| 收货地址 | varchar  | 20  |    |
| 角色   | varchar        | 10  |   |
| 等级   | int            |     |   |
| 个人简介 | varchar        | 250 |   |
| 状态   | int            |     |   |
| 余额   | decimal(20, 2) |     |   |

  商品图表
| 数据项   | 类型      | 长度  | 备注  |
|-------|---------|-----|-----|
| 图片id  | int     |     | 主键  |
| 图片url | varchar | 250 |     |
| 商品id  | int     |     | 商品表 |

  订单表
| 数据项  | 类型             | 长度  | 备注      |
|------|----------------|-----|---------|
| 订单id | int            |     | 主键      |
| 购买人  | int            |     | user    |
| 发货人  | int            |     | user    |
| 创建时间 | detetime |    | |
| 收货地址 | varchar        | 100 |         |
| 发货地址 | varchar        | 100 |         |
| 订单状态 | int            |     |         |
| 支付金额 | decimal(20 ,2) |     |         |
| 备注   | varchar        | 250 |         |
| 商品   | int            |     | product |

收藏表
| 数据项  | 类型  | 长度 | 备注      |
|------|-----|----|---------|
| 收藏id | int |    | 主键      |
| 收藏时间 | detetime |    | |
| 收藏人  | int |    | user    |
| 收藏商品 | int |    | product |


购物车表
| 数据项   | 类型       | 长度 | 备注      |
|-------|----------|----|---------|
| 购物车id | int      |    | 主键      |
| 商品    | int      |    | product |
| 用户    | int      |    | user    |
| 创建时间  | datetime |    |         |
| 商品数量  | int      |    |         |

未送达消息表
| 数据项   | 类型       | 长度 | 备注      |
|-------------|---------|---|---|
| 发送者id | int     |   |   |
| 消息内容  | varchar | 250  |   |
| 接收者id  | int     |   |   |







