#### 总概括：
![总概括](https://user-images.githubusercontent.com/21126771/131376994-5638b9de-eabd-4450-a924-2fba6c5252da.png)

#### IOC容器的初始化：
![IOC容器的初始化](https://user-images.githubusercontent.com/21126771/131377082-b291ef92-bedb-453d-92cf-c1db1de66b82.png)

#### IOC容器的依赖注入：
![IOC容器的依赖注入](https://user-images.githubusercontent.com/21126771/131377094-82af9a3b-b3cd-4251-90ce-c0619c6a380d.png)

#### spring的MVC执行原理：
1.spring mvc将所有的请求都提交给DispatcherServlet,它会委托应用系统的其他模块负责对请求 进行真正的处理工作。
2.DispatcherServlet查询一个或多个HandlerMapping,找到处理请求的Controller.
3.DispatcherServlet请请求提交到目标Controller
4.Controller进行业务逻辑处理后，会返回一个ModelAndView
5.Dispathcher查询一个或多个ViewResolver视图解析器,找到ModelAndView对象指定的视图对象
6.视图对象负责渲染返回给客户端。
 
优点：

1.使用Spring的IOC容器，将对象之间的依赖关系交给Spring，降低组件之间的耦合性，让我们更专注于应用逻辑

2.可以提供众多服务，事务管理，WS等。

3.AOP的很好支持，方便面向切面编程。

4.对主流的框架提供了很好的集成支持，如Hibernate,Struts2,JPA等

5.Spring DI机制降低了业务对象替换的复杂性。

6.Spring属于低侵入，代码污染极低。

7.Spring的高度可开放性，并不强制依赖于Spring，开发者可以自由选择Spring部分或全部

SpringMVC执行流程：
![Spring MVC执行流程](https://user-images.githubusercontent.com/21126771/131377307-21881ec6-145f-407d-bdc0-81cd943bbcb9.png)

用户发起请求到前端控制器（Controller）
前端控制器没有处理业务逻辑的能力，需要找到具体的模型对象处理（Handler），到处理器映射器（HandlerMapping）中查找Handler对象（Model）。
HandlerMapping返回执行链，包含了2部分内容： ① Handler对象、② 拦截器数组
前端处理器通过处理器适配器包装后执行Handler对象。
处理业务逻辑。
Handler处理完业务逻辑，返回ModelAndView对象，其中view是视图名称，不是真正的视图对象。
将ModelAndView返回给前端控制器。
视图解析器（ViewResolver）返回真正的视图对象（View）。
（此时前端控制器中既有视图又有Model对象数据）前端控制器根据模型数据和视图对象，进行视图渲染。
返回渲染后的视图（html/json/xml）返回。
给用户产生响应。
