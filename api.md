# 213
公共参数：
必选：

id ： 100 //用户id
authentication ： 鉴权码 //通过用户id和密码鉴权，避免用户操作他人信息

API说明：
1商家相关

1.1商家信息

url: $HOME/copartner
方法：
GET：获取商家信息

1.2商家库存信息

url: $HOME/copartner/stocks
可选参数：
q ： xxx //用关键字查询相关教材的库存
方法：
GET：获取商家全部库存信息
POST：新增一个商品信息，返回商品ID

1.3商家库存信息

url: $HOME/copartner/stock/id
id：图书编号
方法：
GET： 返回对应教材的库存
PUT：更新对应教材的库存
DELETE：删除对应教材的信息

1.4商家销售信息

url:$HOME/copartner/sell
可选参数：
from:开始日期
to:结束日期
方法：
GET：获取商家销售信息

2图书相关

2.1获取图书信息

url:$HOME/book
q：//查询关键字
可选参数：
name:书名
press:出版社
isbn:ISBN号
方法：
GET：获取图书完整信息

2.2获取图书id

url:$HOME/bookid
isbn://图书ISBN号
方法：
GET：通过ISBN号查询，优先查询本地数据库，如果查询不到再通过外部api获取图书详细信息并存入本地数据库，新增bookid，并返回bookid，查询不到返回错误。
POST：GET方法查询不到时使用，手动新增图书信息，生成bookid，并返回新bookid。
