1. Tomcat整体架构和处理请求流程解析

   Tomcat是Servlet容器 


Plineline

​	Valve

Engine--List<Host>

​	虚拟主机：Host--List<Context>

​			Pieline--List<Value>

​			应用容器：Context--List<Wrapper>

​				Wrapper--List<Servlet>

服务器A--->服务器B

数据+IP

通过TCP协议（可靠）

Socket --> HTTP协议 -->解析 --> Request

HTTP(请求行，请求头，请求体)

数据 --> 

2. Tomcat中关于长连接的底层原理与源码实现
3. Tomcat中自定义类加载器的使用与源码实现
4. Tomcat请求处理详解
5. Tomcat启动过程
6. Tomcat中Session功能的实现
7. Tomcat中JSP功能的实现