# NetCore22Middleware
Net Core 22 Middleware.

ASP.NET Core Middleware是在应用程序处理管道pipeline中用于处理请求和操作响应的组件。
每个组件：
在pipeline中判断是否将请求传递给下一个组件
在处理管道的下个组件执行之前和之后执行一些工作， HttpContxt对象能跨域请求、响应的执行周期.
Ex:

在项目开发的过程中，为了满足需求，还是有许多功能要自己“发明”，也就是已有技术的组(qi)合ji)运(yin)用(qiao)。本例先讲讲如果用中间件开发所有CMS都需要的服务端静态缓存方法。

CMS系统的一大痛点是一个页面要查询的内容很多，所以常常为了减轻服务器压力，都会使用到各种缓存技术。比如静态文件的CDN缓存、客户端缓存、还有就是服务端静态化缓存。

服务端静态化缓存在这里指的是把页面事先生成出来保存为静态文件，当用户请求服务器时，可以直接把页面输出给用户，而不再进行查询数据库之类的操作，已达到提高响应速度、减轻服务器压力的效果。

由于服务端静态化缓存的实现核心是需要拦截请求并且直接返回HTML内容，在MVC5时代，我们可以用过滤器（Filter）来处理.而在ASP.NET Core中，我们也可以在Filte中实现，但是，更方便、更牛、更快的方式就是在中间件中实现了。
