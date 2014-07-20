# 公共参数：
### 必选：
**id** ： 100 //用户id

**authentication**： 鉴权码 //通过用户id和密码鉴权，避免用户操作他人信息


# API说明：

## 1 用户相关
### 1.1 user
**url**:$HOME/user

#### GET方法 ####
获取用户信息
##### 必选参数 #####
**id**:用户id,长度必须为24位
##### 返回 #####
**成功：**

**失败：**

### 1.2 user/login
**url**:$HOME/user/login

#### GET方法 ####
获取用户登录状体
##### 返回 #####
**成功：**

**失败：**















## 1商家相关
### 1.1商家信息
<strong>url</strong>: $HOME/copartner
方法：
<strong>GET</strong>：获取商家信息

<h3>1.2商家库存信息</h3>
<strong>url</strong>: $HOME/copartner/stocks
可选参数：
<strong>q</strong> ： xxx //用关键字查询相关教材的库存
方法：
<strong>GET</strong>：获取商家全部库存信息
<strong>POST</strong>：新增一个商品信息，返回商品ID

<h3>1.3商家库存信息</h3>
<strong>url</strong>: $HOME/copartner/stock/id
<strong>id</strong>：图书编号
方法：
<strong>GET</strong>： 返回对应教材的库存
<strong>PUT</strong>：更新对应教材的库存
<strong>DELETE</strong>：删除对应教材的信息

<h3>1.4商家销售信息</h3>
<strong>url</strong>:$HOME/copartner/sell
可选参数：
<strong>from</strong>:开始日期
<strong>to</strong>:结束日期
方法：
<strong>GET</strong>：获取商家销售信息

<h2>2图书相关</h2>
<h3>2.1获取图书信息</h3>
<strong>url</strong>:$HOME/book
<strong>q</strong>：//查询关键字
可选参数：
<strong>name</strong>:书名
<strong>press</strong>:出版社
<strong>isbn</strong>:ISBN号
方法：
<strong>GET</strong>：获取图书完整信息

<h3>2.2获取图书id</h3>
<strong>url</strong>:$HOME/bookid
<strong>isbn</strong>://图书ISBN号
方法：
<strong>GET</strong>：通过ISBN号查询，优先查询本地数据库，如果查询不到再通过外部api获取图书详细信息并存入本地数据库，新增bookid，并返回bookid，查询不到返回错误。
<strong>POST</strong>：GET方法查询不到时使用，手动新增图书信息，生成bookid，并返回新bookid。
