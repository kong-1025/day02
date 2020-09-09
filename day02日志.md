一.今天实现了商品分类查询

​	1.首先导入SQL数据，在`leyou-item-interface`中添加category实体类

​	2.编写一个controller一般需要知道四个内容：

- 请求方式：决定我们用GetMapping还是PostMapping

- 请求路径：决定映射路径

- 请求参数：决定方法的参数

- 返回值结果：决定方法的返回值

  3.一般service层我们会定义接口和实现类

  4.我们使用通用mapper来简化开发：在启动类上添加一个扫描包功能：



二.实现了跨域问题

​	利用cors解决跨域

1.在`leyou-gateway`中编写一个配置类，并且注册CorsFilter：

​	什么是corsair：

CORS是一个W3C标准，全称是"跨域资源共享"（Cross-origin resource sharing）。

它允许浏览器向跨源服务器，发出[`XMLHttpRequest`](http://www.ruanyifeng.com/blog/2012/09/xmlhttprequest_level_2.html)请求，从而克服了AJAX只能[同源](http://www.ruanyifeng.com/blog/2016/04/same-origin-policy.html)使用的限制。

CORS需要浏览器和服务器同时支持。目前，所有浏览器都支持该功能，IE浏览器不能低于IE10。

- 浏览器端：

  目前，所有浏览器都支持该功能（IE10以下不行）。整个CORS通信过程，都是浏览器自动完成，不需要用户参与。

- 服务端：

  CORS通信与AJAX没有任何差别，因此你不需要改变以前的业务逻辑。只不过，浏览器会在请求中携带一些头信息，我们需要以此判断是否允许其跨域，然后在响应头中加入一些信息即可。这一般通过过滤器完成即可。



