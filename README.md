# php面试题汇总

结合实际PHP面试，以及网上其他人遇到的问题，尝试提供简洁准确的答案



### php面试题
  - [isset和empty的区别](./docs/php面试题.md#isset和empty的区别)
  - [单引号和双引号的区别](./docs/php面试题.md#单引号和双引号的区别)
  - [error_reporting的作用](./docs/php面试题.md#error_reporting的作用)
  - [include和requirer的区别](./docs/php面试题.md#include和requirer的区别)
  - [php中的sql防注入](./docs/php面试题.md#php中的sql防注入)
  - [常见数组函数](./docs/php面试题.md#常见数组函数)
  - [什么是面向对象](./docs/php面试题.md#什么是面向对象)
  - [对象的主要特征包括](./docs/php面试题.md#对象的主要特征包括)
  - [php怎么实现静态化](./docs/php面试题.md#php怎么实现静态化)
  - [常见的设计模式](./docs/php面试题.md#常见的设计模式)
  - [MySQL、MySQLi、PDO的区别](./docs/php面试题.md#MySQL、MySQLi、PDO的区别)
  - [链式调用实现](./docs/php面试题.md#链式调用实现)
  - [异常处理](./docs/php面试题.md#异常处理)
  - [CSRF和XSS攻击分别是什么](./docs/php面试题.md#CSRF和XSS攻击分别是什么)
  - [抽象类和接口分别是什么](./docs/php面试题.md#抽象类和接口分别是什么)
  - [谈谈对设计模式的了解](./docs/php面试题.md#谈谈对设计模式的了解)
  - [谈谈对微服务的理解](./docs/php面试题.md#谈谈对微服务的理解)
  - [说说垃圾回收机制](./docs/php面试题.md#说说垃圾回收机制)
  - [高并发解决方案](./docs/php面试题.md#高并发解决方案)
  - [什么是时序攻击](./docs/php面试题.md#什么是时序攻击)
  - [面相对象的三大特性和五项原则](./docs/php面试题.md#面相对象的三大特性和五项原则)
  - [TCP与UDP的区别](./docs/php面试题.md#TCP与UDP的区别)
  - [PHP5和PHP7的区别](./docs/php面试题.md#PHP5和PHP7的区别)
  - [PHP-FPM的两种模式](./docs/php面试题.md#PHP-FPM的两种模式)
  - [PHP数组底层结构](./docs/php面试题.md#PHP数组底层结构)
  - [HTTPS加密位置](./docs/php面试题.md#HTTPS加密位置)
  - [SSL加密过程](./docs/php面试题.md#SSL加密过程)
  - [魔术方法有哪些](./docs/php面试题.md#魔术方法有哪些)
  - [PHP读取大文件](./docs/php面试题.md#PHP读取大文件)
  - [SESSION与COOKIE的区别](./docs/php面试题.md#SESSION与COOKIE的区别)
  - [HTTP状态中302、403、500代码含义](./docs/php面试题.md#HTTP状态中302、403、500代码含义)
  - [PHP中传值与传引用的区别](./docs/php面试题.md#PHP中传值与传引用的区别)
  - [foo()和@foo()之间有什么区别](./docs/php面试题.md#foo()和@foo()之间有什么区别)
  - [简述php的垃圾收集机制](./docs/php面试题.md#简述php的垃圾收集机制)
  - [echo、print_r、print、var_dump区别](./docs/php面试题.md#echo、print_r、print、var_dump区别)
  - [AJAX的优势是什么](./docs/php面试题.md#AJAX的优势是什么)
  - [PHP如何实现页面跳转](./docs/php面试题.md#PHP如何实现页面跳转)
  - [如何把一个GB2312格式的字符串装换成UTF-8格式](./docs/php面试题.md#如何把一个GB2312格式的字符串装换成UTF-8格式)
  - [对json数据格式的理解](./docs/php面试题.md#对json数据格式的理解)
  - [简述private、protected、public修饰符的访问权限](./docs/php面试题.md#简述private、protected、public修饰符的访问权限)
  - [堆和栈的区别](./docs/php面试题.md#堆和栈的区别)
  - [$this和self、parent这三个关键词分别](./docs/php面试题.md#$this和self、parent这三个关键词分别)
  - [__autoload()方法的工作原理是什么](./docs/php面试题.md#__autoload()方法的工作原理是什么)
  - [简述高并发网站解决方案](./docs/php面试题.md#简述高并发网站解决方案)
  - [串行、并行、并发的区别](./docs/php面试题.md#串行、并行、并发的区别)
  - [http状态码](./docs/php面试题.md#http状态码)
  - [延迟队列怎么实现](./docs/php面试题.md#延迟队列怎么实现)

### php框架相关
  
  - [框架的生命周期](./docs/php框架相关.md#框架的生命周期)
  - [类的自动加载怎么实现](./docs/php框架相关.md#类的自动加载怎么实现)
  - [Composer的功能和实现](./docs/php框架相关.md#Composer的功能和实现)
  - [路由是怎么实现的](./docs/php框架相关.md#路由是怎么实现的)
  - [什么是MVC](./docs/php框架相关.md#什么是MVC)
  - [什么是依赖注入](./docs/php框架相关.md#什么是依赖注入)
  - [模板引擎的原理](./docs/php框架相关.md#模板引擎的原理)

### composer面试题

- [composer的工作原理](./docs/composer.md#composer的工作原理)
- [使用composer创建并部署一个PHP包](./docs/composer.md#使用composer创建并部署一个PHP包)
- [composer的自动加载机制是如何实现的](./docs/composer.md#composer的自动加载机制是如何实现的)
- [如何解决composer依赖冲突的问题](./docs/composer.md#如何解决composer依赖冲突的问题)
- [composer中的require和require-dev有什么区别](./docs/composer.md#composer中的require和require-dev有什么区别)
- [如何优化composer的加载速度](./docs/composer.md#如何优化composer的加载速度)
- [composer的全局安装和局部安装有什么区别](./docs/composer.md#composer的全局安装和局部安装有什么区别)
- [composer的命令行常用命令及其作用](./docs/composer.md#composer的命令行常用命令及其作用)




### mysql面试题

  - [MyISAM和InnoDB的区别](./docs/mysql面试题.md#MyISAM和InnoDB的区别)
  - [索引结构（解释B+树）](./docs/mysql面试题.md#索引结构（解释B+树）)
  - [悲观锁和乐观锁](./docs/mysql面试题.md#悲观锁和乐观锁)
  - [select执行过程](./docs/mysql面试题.md#select执行过程)
  - [事务隔离级别](./docs/mysql面试题.md#事务隔离级别)
  - [索引回表](./docs/mysql面试题.md#索引回表)
  - [索引失效](./docs/mysql面试题.md#索引失效)
  - [分库分表](./docs/mysql面试题.md#分库分表)
  - [读写分离](./docs/mysql面试题.md#读写分离)
  - [PG和Mysql的区别](./docs/mysql面试题.md#PG和Mysql的区别)
  - [MySQL相对于PostgreSQL的优势](./docs/mysql面试题.md#MySQL相对于PostgreSQL的优势)
  - [explain用到那些信息](./docs/mysql面试题.md#explain用到那些信息)
  - [PG和Mysql的区别](./docs/mysql面试题.md#PG和Mysql的区别)
  - [数据类型(int、char、varchar、datetime、text)分别的什么](./docs/mysql面试题.md#数据类型(int、char、varchar、datetime、text)分别的什么**)
  - [varchar和char的区别](./docs/mysql面试题.md#varchar和char的区别)
  - [主键、外键和索引的区别](./docs/mysql面试题.md#主键、外键和索引的区别)
  - [MySQL多表联合查询](./docs/mysql面试题.md#MySQL多表联合查询)

### redis面试题

  - [常用的数据类型有哪些](./docs/redis面试题.md#常用的数据类型有哪些)
  - [常用命令有哪些](./docs/redis面试题.md#常用命令有哪些)
  - [应用场景](./docs/redis面试题.md#应用场景)
  - [数据过期策略](./docs/redis面试题.md#数据过期策略)
  - [内存淘汰机制](./docs/redis面试题.md#内存淘汰机制)
  - [事务机制](./docs/redis面试题.md#事务机制)
  - [缓存击穿](./docs/redis面试题.md#缓存击穿)
  - [缓存穿透](./docs/redis面试题.md#缓存穿透)
  - [缓存雪崩](./docs/redis面试题.md#缓存雪崩)
  - [分布式锁](./docs/redis面试题.md#分布式锁)
  - [集群](./docs/redis面试题.md#集群)
  - [持久化](./docs/redis面试题.md#持久化)
  - [rdb优点和缺点](./docs/redis面试题.md#rdb优点和缺点)
  - [AOF优点和缺点](./docs/redis面试题.md#AOF优点和缺点)
  - [redis字符串类型底层实现](./docs/redis面试题.md#redis字符串类型底层实现)
  - [保证Redis缓存和数据库数据的一致性](./docs/redis面试题.md#保证Redis缓存和数据库数据的一致性)

### 数据结构与算法

### 设计模式

### linux面试题

  - [常用的Linux命令](./docs/linux面试题.md#常用的Linux命令)

### web安全

### 架构

  - [分布式和集群的概念](./docs/架构.md#分布式和集群的概念)


### 送命题
  - [对加班怎么看](./docs/其他.md#你对加班怎么看)
  - [请自我介绍一下](./docs/其他.md#请自我介绍一下)
  - [你还有什么问题想问我吗](./docs/其他.md#你还有什么问题想问我吗)
  - [说一下你的优点和缺点吧](./docs/其他.md#说一下你的优点和缺点吧)
  - [给我选择你的理由](./docs/其他.md#给我选择你的理由)
  - [你的职业规划是什么](./docs/其他.md#你的职业规划是什么)
  - [上家公司离职的原因是什么](./docs/其他.md#上家公司离职的原因是什么)
  - [工作遇到的最大困难以及解决方法是什么](./docs/其他.md#工作遇到的最大困难以及解决方法是什么)
  - [工作中觉得最有成就感事是什么](./docs/其他.md#工作中觉得最有成就感事是什么)
  



### 参与贡献

fork 当前库到你的名下   
在你的本地修改完成审阅过后提交到你的仓库        
提交 PR 并描述你的修改，等待合并      

### License
MIT license