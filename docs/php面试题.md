### isset和empty的区别

isset和empty的区别主要在于它们的功能和用法。以下是详细内容：
- empty     
它用于检查一个变量的值是否为空，包括空字符串、0、NULL、FALSE、array()、对象（没有任何属性）等。如果变量不存在，empty() 返回 TRUE；如果变量存在且其值为空，则返回 FALSE。1234
- isset     
  它用于检测变量是否已经设置，即使变量的值为NULL，isset() 也会返回 TRUE。
  如果变量未设置，isset() 返回 FALSE。需要注意的是，如果一个变量被 unset() 释放，那么使用 isset() 判断该变量将返回 FALSE。
总结来说，empty() 用于判断变量的值是否为空，而 isset() 用于判断变量是否已经设置。

### 单引号和双引号的区别

双引号可以被分析器解析，单引号则不行

### error_reporting的作用

error_reporting 是 PHP 中的一个函数，用于设置应该报告何种错误。

这个函数可以设置错误报告的级别，并对应地显示错误信息。

解释：

error_reporting() 函数用于设置应该报告何种错误。

这个函数有两种用法：一种是作为函数调用，另一种是作为一个指令使用。

作为函数调用时，可以接受一个参数，这个参数可以是一个整数或者是一个预定义的常量。

作为指令使用时，不需要参数，而是需要一个整数值或者使用 | （或）运算符来组合多个常量。

解决方法：

修改 php.ini 文件中的 error_reporting 配置项，设置为 E_ALL，这样可以显示所有错误和警告。

在 PHP 脚本中，使用 error_reporting(E_ALL); 来显示所有错误和警告。

如果只想报告特定的错误，可以使用位掩码来指定错误级别。例如，error_reporting(E_ERROR | E_WARNING); 会报告错误和警告。

如果想关闭错误报告，可以使用 error_reporting(0);。

注意：在生产环境中，通常不建议显示或记录错误信息，因为这可能会泄露敏感信息。在开发环境中，应该开启错误报告，以便快速发现和解决问题。

### include和requirer的区别

1，require在程序解释执行前被加载，被加载的内容，在程序解释执行过程中被经常使用；

include则是在解释执行过程中，需要使用某些内容使用，include加载；由此可见，某些内容经常使用，可以使用require；

如果每次执行代码是读取不同的文件，或者有通过一组文件迭代的循环，就使用include。

2，include引入文件失败时候，警告，程序继续执行；require引入文件出错时候，错误，停止执行。


### 常见数组函数

- array_count_values — 统计数组中所有的值

- array_flip — 交换数组中的键和值

- array_merge — 合并一个或多个数组

- array_multisort — 对多个数组或多维数组进行排序

- array_pad — 以指定长度将一个值填充进数组

- array_pop — 弹出数组最后一个单元(出栈)

- array_push — 将一个或多个单元压入数组的末尾(入栈)

- array_rand — 从数组中随机(伪随机)取出一个或多个单元

- array_keys — 返回数组中部分的或所有的键名

- array_values — 返回数组中所有的值

- count — 计算数组中的单元数目，或对象中的属性个数

- sort — 对数组排序

### php中的sql防注入

1、addslashes()方法对参数预处理

addslashes() 函数返回在预定义字符之前添加反斜杠的字符串。

预定义字符有

单引号（'）

双引号（"）

反斜杠（\）

NULL


存在问题

addslashes 函数仅仅是将某些字符进行了转义，但并没有考虑到不同字符集的编码问题。因此，在使用 addslashes 函数时，可能会出现以下情况：

如果使用的是非 ASCII 字符集，如中文、日语等字符集，那么 addslashes 函数可能会导致字符串变得无效或者出现乱码。

addslashes 函数并不能转义所有可能引起 SQL 注入的字符。例如，使用 %、_、- 等字符可以进行模糊查询，而这些字符在 addslashes 函数中并没有被转义。

addslashes 函数并不能防止双重转义问题。如果用户已经对输入进行了转义，再使用 addslashes 函数可能会导致出现双重转义的问题，从而使字符串变得无效。

2、使用mysqli_real_escape_string()函数转义


```php
$username = mysqli_real_escape_string($conn, $_POST['username']);
$password = mysqli_real_escape_string($conn, $_POST['password']);
$sql = "SELECT * FROM users WHERE username = '$username' AND password = '$password'";
$result = mysqli_query($conn, $sql);
```



3、使用参数化查询 (Prepared Statements) 或者绑定参数（Binding Parameters）的方法

$stmt = $pdo->prepare('SELECT * FROM users WHERE username = ? AND password = ?');
$stmt->execute([$username, $password]);

为什么预处理和参数化查询可以防止sql注入呢?

在mysql5.1后，提供了类似于jdbc的预处理-参数化查询。它的查询方法是：

a. 先预发送一个sql模板过去

b. 再向mysql发送需要查询的参数

发送的参数会自动过滤用户输入中的特殊字符

### 什么是面向对象

面向对象（Object Oriented，简称 OO）是一种计算机编程的思想和方法，它的核心是将程序中的行为主体定义为对象。

面向对象编程（Object Oriented Programming，简称 OOP）则是使用面向对象思想进行程序设计的一种方法，以对象作为基本的结构单位。

封装、继承和多态,其中封装是将数据和操作封装在一个对象中，避免了外部对内部数据的直接访问，提高了安全性和可维护性。

继承是一种可以复用已有代码的方式，子类可以继承父类的数据和操作，并且可以根据需要进行修改或者扩展。

多态是指同一个消息可以被不同类型的对象接收并产生不同的行为，实现了代码的灵活性和扩展性。


### 对象的主要特征包括：

对象的主要特征

对象的主要特征包括：


- 封装。对象通常包含数据和操作这些数据的函数（方法）。封装是指将数据和操作封装在一起，使得数据对外的访问和操作受到限制，只能通过对象提供的公共接口进行。

- 继承。继承是一种机制，允许对象从其超类（父类）继承属性和方法，从而减少重复代码并增加代码的可重用性。

- 多态。多态是指一个父对象可以与多个子对象绑定，并根据当前绑定的子对象的特性以不同的方式执行操作。这使得编程更加灵活和开放。

- 动态性。对象通常是可以在运行时创建、修改和销毁的，这增加了代码的灵活性和适应性。

- 唯一性。在面向对象系统中，每个对象都是独一无二的实例，即使它们属于相同的类。

- 主动性。对象能够主动地执行操作，访问其数据，并与外部系统进行交互。

- 模块独立性。良好的面向对象设计使得系统的各个模块（对象）之间耦合程度较低，提高了系统的可维护性和可复用性。

这些特征共同构成了面向对象编程的核心概念，使得编程更加接近于人类解决问题的自然方式。

### php怎么实现静态化

在PHP中可以通过使用缓存技术来实现页面的静态化。常见的方法有两种：

生成HTML文件：将动态生成的内容保存为静态的HTML文件，下次访问时直接返回该HTML文件而不再需要经过服务器处理。这样可以大大提高网站的性能和加载速度。以下是一个示例代码：

```php
<?php
$cacheFile = 'path/to/cached_file.html'; // 设置缓存文件路径及名称
if (is_readable($cacheFile)) {
    $lastModifiedTime = filemtime($cacheFile); // 获取上次修改时间
    if ($lastModifiedTime > time()) {
        header('Last-Modified: '.gmdate('D, d M Y H:i:s', $lastModifiedTime).' GMT');
        readfile($cacheFile); // 输出缓存文件内容并结束程序运行
        exit;
    } else {
        unlink($cacheFile); // 如果缓存文件已过期则删除
    }
}
// 其他业务逻辑...
ob_start(); // 开始缓存输出内容
?>
<!DOCTYPE html>
<html>
<!-- HTML内容 -->
</html>
<?php
$content = ob_get_contents(); // 获取缓存的内容
ob_end_clean(); // 清空缓存
file_put_contents($cacheFile, $content); // 写入缓存文件
echo $content; // 输出最新的HTML内容
?>
```

使用模版引擎：利用模版引擎（如Smarty、Blade等）将动态数据与静态模版分离，然后根据参数或条件判断是否重新编译模版并生成静态页面。

以下是一个基于Smarty的示例代码：

```php
<?php
require_once('smarty/libs/Smarty.class.php');
$smarty = new Smarty();
$smarty->compile_check = true; // 自动检查模版更新
$smarty->template_dir = 'templates/'; // 设置模版目录
$smarty->compile_dir = 'compiled/'; // 设置编译目录
$smarty->config_dir = ''; // 配置文件目录
$smarty->left_delimiter = '{'; // 左定界符
$smarty->right_delimiter = '}'; // 右定界符

$data['title'] = "Hello World";
$data['message'] = "This is a static page.";

$smarty->assign("data", $data);
$smarty->display('static_page.tpl'); // 显示静态页面
?>
```

### 常见的设计模式

- 工厂模式 。工厂模式是一种创建型模式，它定义了一个工厂类，用于创建对象，而不是在代码中直接实例化对象。
  
- 单例模式 。单例模式是一种创建型模式，它保证一个类只有一个实例，并提供一个全局访问点。
  
- 观察者模式 。观察者模式是一种行为型模式，它定义了一种一对多的依赖关系，使得多个观察者对象可以同时监听一个主题对象。
  
- 适配器模式 。适配器模式是一种结构型模式，它允许将一个类的接口转换成客户端所期望的另一个接口。
  
- 装饰器模式 。装饰器模式是一种结构型模式，它允许在不改变对象自身的基础上，动态地添加功能。
  
- 策略模式 。策略模式是一种行为型模式，它定义了一系列算法，并将每个算法封装起来，使得它们可以互相替换。
  
- 模板方法模式 。模板方法模式是一种行为型模式，它定义了一个算法的骨架，将一些步骤延迟到子类中实现。



### MySQL、MySQLi、PDO的区别

- MySQL
    允许 PHP 应用与 MySQL 数据库交互的早期扩展
    提供了一个面向过程的接口，不支持后期的一些特性
  
- MySQLi
    面向对象接口
    prepared 语句支持
    多语句执行支持
    事务支持
    增强的调试能力
  
- PDO
    PHP 应用中的一个数据库抽象层规范
    PDO 提供一个统一的 API 接口，无须关心数据库类型
    使用标准的 PDO API，可以快速无缝切换数据库

### 链式调用实现

类定义一个内置变量，让类中其他定义方法可访问到

### 异常处理

set_exception_handler — 设置用户自定义的异常处理函数

使用 try / catch 捕获

### CSRF和XSS攻击分别是什么

CSRF攻击：跨站域请求伪造

简单来说就是cookie劫持，用户通过cookie实现登录，将cookie信息带到了携带病毒的网站，病毒网站通过js代码给原网站发送请求。

防御方法：每个网页表单中增加一个csrf_token，cookie中同时增加相同的csrf_token，通过服务器代码中间件验证csrf_token是否相同来进行拦截。

XSS攻击：跨站点脚本注入

黑客在网站填写表单时，填入了js脚本，导致在展示的时候，注入了跳转到其他仿原网站的含病毒的网站。
防御方法：

1.表单提交的时候，过滤 js、html等相关脚本的数据

2.客户输入的内容进行验证，包括URL，请求头，提交的数据，过滤指定特殊字符串   

3.内容输出时，进行urlencode处理       

4.cookie防盗，cookie中不存储客户隐私相关信息，比如密码、姓名、email，绑定cookie和系统ip来降低cookie泄漏的风险     


### 抽象类和接口分别是什么

- 抽象类：
  
    用abstract修饰的类，没有给足够的信息去描述具体的对象，这样的类就是抽象类，抽象类无法被实例化，但仍有变量，方法，构造方法。
  
    抽象类只能用作基类，表示的是一种继承关系。
  
- 抽象方法：
  
    用abstract修饰的方法，抽象方法只有声明，没有具体实现，如果某个类包含抽象方法，那么它一定是抽象类
  
- 接口：
  
    用interface修饰的类，接口是一种特殊的抽象类，只包含常量和方法名，没有变量和方法的实现，无法被实例化。
  
    为什么会有接口：类只有一个父类，使用接口可以进行多继承
  
- 抽象类与接口的联系和区别：
  
    二者都可以定义抽象方法，都没有具体实现，需要继承，重写。
  
    因为类只能有一个父类，接口解决了单继承的局限性。
  
    抽象类可以定义普通方法，接口可以定义default方法。

### 谈谈对设计模式的了解

面向对象开发过程中，总结出来的解决一般问题的方案。

常见的设计模式有三大类：

- 创建型：
  
对象实例化的模式，创建型模式用于解耦对象的实例化过程。     
典型的小类有：单例模式，工厂模式，建造者模式
  
- 结构型：
  
把类或对象结合在一起形成一个更大的结构。    
典型的小类有：适配器模式，装饰模式，门面模式
  
- 行为型；
  
类和对象如何交互，及划分责任和算法。  
典型的小类有：策略模式，观察者模式，解释器模式

### 谈谈对微服务的理解

概念：把⼀个⼤型的单个应⽤程序和服务拆分为数个甚⾄数⼗个的⽀持服务，它可扩展单个组件⽽不是整个的应⽤程序堆栈，从⽽满⾜服务等级协议。

### 说说垃圾回收机制

正常的生命周期结束后内存就会释放。
引用计数，一个变量值的内存对象，在引用给另一个变量时，引用计数器会+1，unset处理后会-1，当计数器为0时，内存对象进行销毁，垃圾回收完成
循环回收算法，根缓存区存满时，执行循环查找，默认大小10000，强制回收内存对象。

### 高并发解决方案

- 前端：异步请求+静态化资源+cdn+varnish

- 后端：请求队列+轮询分发+负载均衡+共享缓存

- 数据层：redis缓存+数据分表+写队列

- 存储：raid阵列+热备

- 网络：dns轮询+DDOS攻击防护

### 什么是时序攻击

在密码学中,时序攻击是一种侧信道攻击,攻击者试图通过分析加密算法的时间执行来推导出密码。        
每一个逻辑运算在计算机需要时间来执行,根据输入不同,精确测量执行时间,根据执行时间反推出密码。     
通过计算返回的速度就知道了大概是哪一位开始不同的，这样就实现了电影中经常出现的按位破解密码的场景。       
防御方法：密码比较时，使用hash_qeuals（hash加密进行比较），这样无论字符串是否相等，函数的时间消耗是恒定的。       

### 魔术方法有哪些
__construct()：创建对象时触发
__destruct() ：对象被销毁时触发
__sleep() ：在对象被序列化的过程中自动调用，且发生在序列化之前
__wakeup()： 该魔术方法在反序列化的时候自动调用，且发生在反序列化之前
__get() ：用于从不可访问或不存在的属性读取数据
__set() ：用于将数据写入不可访问或不存在的属性
__call() ：在对象上下文中调用不可访问的方法时触发
__callStatic() ：在静态上下文中调用不可访问的方法时触发
__toString()：在对象当做字符串的时候会被调用。
__invoke() ：当尝试将对象调用为函数时触发

### 面相对象的三大特性和五项原则
基本特征是：封装、继承、多态
封装，也就是把客观事物封装成抽象的类，并且类可以把⾃⼰的数据和⽅法只让可信的类或者对象操作，对不可信的进⾏信息隐藏。
继承是指这样⼀种能⼒：它可以使⽤现有类的所有功能，并在⽆需重新编写原来
的类的情况下对这些功能进⾏扩展。
多态性：允许将⼦类类型的指针赋值给⽗类类型的指针。

实现多态，有⼆种⽅式，覆盖，重载。
覆盖，是指⼦类重新定义⽗类的虚函数的做法。
重载，是指允许存在多个同名函数，⽽这些函数的参数表不同（或许参数个数不同，或许参数类型不同，或许两者都不同）。
五项原则：
单一职责原则SRP(Single Responsibility Principle)
是指一个类的功能要单一，不能包罗万象。
开放封闭原则OCP(Open－Close Principle)
一个模块在扩展性方面应该是开放的而在更改性方面应该是封闭的。
里氏替换原则LSP(the Liskov Substitution Principle)
子类应当可以替换父类并出现在父类能够出现的任何地方。
依赖倒置原则DIP(the Dependency Inversion Principle)
具体依赖抽象，上层依赖下层。
接口分离原则ISP(the Interface Segregation Principle)
模块间要通过抽象接口隔离开，而不是通过具体的类强耦合起来。
迪米特法则LOD（Law of Demeter）
又叫作最少知识原则，一个类对于其他类知道的越少越好，就是说一个对象应当对其他对象有尽可能少的了解,只和朋友通信，不和陌生人说话。


### TCP与UDP的区别
![img.png](img.png)

僵尸进程产生的原因，排查方法和解决方案

### PHP5和PHP7的区别
1、性能提升：PHP7比PHP5.0性能提升了两倍。
2、以前的许多致命错误，现在改成抛出异常。
3、PHP 7.0比PHP5.0移除了一些老的不在支持的SAPI（服务器端应用编程端口）和扩展。
4、PHP 7.0比PHP5.0新增了空接合操作符。(??)
5、PHP 7.0比PHP5.0新增加了结合比较运算符。a<=>b  当a等于b是，返回0，a小于b时，返回1，a大于b时，返回-1
6、PHP 7.0比PHP5.0新增加了函数的返回类型声明。
7、PHP 7.0比PHP5.0新增加了标量类型声明。简单数据类型声明 string int 等
8、PHP 7.0比PHP5.0新增加匿名类和匿名函数。当函数的参数类型为指定类时，可以直接用 new class implements 类名{ 类内容 } 作为参数
9、错误处理和64位支持

### PHP-FPM的两种模式
php-fpm的进程数也是可以根据设置分为动态和静态的。
一种是直接开启指定数量的php-fpm进程，不再增加或者减少；
另一种则是开始的时候开启一定数量的php-fpm进程，当请求量变大的时候，动态的增加php-fpm进程数到上限，当空闲的时候自动释放空闲的进程数到一个下限。

### PHP数组底层结构
数组是PHP中非常强大、灵活的一种数据类型，它的底层实现为散列表(HashTable，也称作：哈希表)，除了我们熟悉的PHP用户空间的Array类型之外，内核中也随处用到散列表，比如函数、类、常量、已include文件的索引表、全局符号表等都用的HashTable存储。

### HTTPS加密位置
传输层，HTTP协议采用明文传输信息，存在信息窃听、信息篡改和信息劫持的风险，而协议TLS/SSL具有身份验证、信息加密和完整性校验的功能，可以避免此类问题发生。
TLS/SSL全称安全传输层协议Transport Layer Security, 是介于TCP和HTTP之间的一层安全协议，不影响原有的TCP协议和HTTP协议，所以使用HTTPS基本上不需要对HTTP页面进行太多的改造。
Cookie过长
单条cookie记录能够存储的最大数据量为4KB左右，超过就有存不进cookie。
localStorage和sessionStorage，它们两个可以存储5MB的数据，但是需要以string类型存储，localStorage存储的数据会一直存在，而sessionStorage只会存在当前会话中，会话结束sessionStorage中的数据会清空。

### SSL加密过程
三次握手
客户端请求服务端响应CA证书，客户端用证书公钥加密自己生成的主密钥，生成新的密钥发送给服务端，服务端用自己的密钥解密得到主密钥
客户端和服务器分别生成两个密钥用于加密会话数据和会话MAC
数据传输时，分片传输加密会话和会话MAC

### PHP读取大文件
采用生成器yield进行逐行返回

### SESSION与COOKIE的区别

http无状态协议，不能区分用户是否是从同一个网站上来的，同一个用户请求不同的页面不能看做是同一个用户。B、SESSION存储在服务器端，COOKIE保存在客户端。Session比较安全，cookie用某些手段可以修改，不安全。Session依赖于cookie进行传递。禁用cookie后，session不能正常使用。Session的缺点：保存在服务器端，每次读取都从服务器进行读取，对服务器有资源消耗。Session保存在服务器端的文件或数据库中，默认保存在文件中，文件路径由php配置文件的session.save_path指定。Session文件是公有的。




### HTTP状态中302、403、500代码含义

一二三四五原则:（即一：消息系列；二：成功系列；三：重定向系列；四：请求错误系列；五：服务器端错误系列。）302:临时转移成功，请求的内容已转移到新位置403:禁止访问 500:服务器内部错误 401：代表未授权。


### PHP中传值与传引用的区别

按值传递：函数范围内对值的任何改变在函数外部都会被忽略按引用传递：函数范围内对值的任何改变在函数外部也能反映出这些修改优缺点：按值传递时，php必须复制值。特别是对于大型的字符串和对象来说，这将会是一个代价很大的操作。按引用传递则不需要复制值，对于性能提高很有好处。


### AJAX的优势是什么？

ajax是异步传输技术，可以通过javascript实现，也可以通过JQuery框架实现，实现局部刷新，减轻了服务器的压力，也提高了用户体验。

### 在程序的开发中，如何提高程序的运行效率？

优化SQL语句，查询语句中尽量不使用select *，用哪个字段查哪个字段；少用子查询可用表连接代替；少用模糊查询；B、数据表中创建索引；C、对程序中经常用到的数据生成缓存。


### 对于大流量的网站,您采用什么样的方法来解决访问量问题?

A、有效使用缓存，增加缓存命中率B、使用负载均衡C、对静态文件使用cdn进行存储和加速D、想法减少数据库的使用E、查看出现统计的瓶颈在哪里F、反向代理

### foo()和@foo()之间有什么区别?

@代表所有warning忽略


### 简述php的垃圾收集机制。

php中的变量存储在变量容器zval中，zval中除了存储变量类型和值外，还有is_ref和refcount字段。refcount表示指向变量的元素个数，is_ref表示变量是否有别名。如果refcount为0时，就回收该变量容器。如果一个zval的refcount减1之后大于0，它就会进入垃圾缓冲区。当缓冲区达到最大值后，回收算法会循环遍历zval，判断其是否为垃圾，并进行释放处理。

### echo、print_r、print、var_dump区别

echo：语句结构；print：是函数，有返回值print_r：能打印数组，对象var_dump:能打印对象数组，并且带数据类型

### PHP如何实现页面跳转？

方法一：php函数跳转，缺点，header头之前不能有输出，跳转后的程序继续执行，可用exit中断执行后面的程序。header("Location:网址");//直接跳转header("refresh:3;url=http://www.jsdaima.com");//三秒后跳转方法二：利用metaecho"";


### 如何把一个GB2312格式的字符串装换成UTF-8格式

iconv('GB2312','UTF-8','js代码（http://www.jsdaima.com）是IT资源下载与IT技能学习平台。');?>

### 对json数据格式的理解

JSON(javascript object Notation)是一种轻量级的数据交换格式，json数据格式固定，可以被多种语言用作数据的传递。

### 简述private、protected、public修饰符的访问权限

private : 私有成员, 在类的内部才可以访问。 protected : 保护成员，该类内部和继承类中可以访问。public : 公共成员，完全公开，没有访问限制。

### 堆和栈的区别

A、堆是程序运行期间动态分配的内存空间，你可以根据程序的运行情况确定要分配的堆内存的大小；B、栈是编译期间就分配好的内存空间，因此你的代码中必须就栈的大小有明确的定义。

### $this和self、parent这三个关键词分别

$this 当前对象self 当前类parent 当前类的父类
$this在当前类中使用,使用->调用属性和方法self也在当前类中使用，不过需要使用::调用parent在类中使用

### __autoload()方法的工作原理是什么

答：使用这个魔术函数的基本条件是类文件的文件名要和类的名字保持一致。



当程序执行到实例化某个类的时候，如果在实例化前没有引入这个类文件，那么就自动执行__autoload()函数。



这个函数会根据实例化的类的名称来查找这个类文件的路径，当判断这个类文件路径下确实存在这个类文件后



就执行include或者require来载入该类，然后程序继续执行，如果这个路径下不存在该文件时就提示错误。



使用自动载入的魔术函数可以不必要写很多个include或者require函数。


### 简述高并发网站解决方案

A、前端优化（CND加速、建立独立图片服务器）B、服务端优化（页面静态化、并发处理[异步|多线程]、队列处理）C、数据库优化（数据库缓存[Memcachaed|Redis]、读写分离、分库分表、分区）D、Web服务器优化（负载均衡、反向代理）


### 串行、并行、并发的区别


串行：执行多个任务时，各个任务按顺序执行，完成一个之后才能进行下一个 并行：多个任务在同一时刻执行 并发：同一时刻需要执行多个任务

### 发起HTTP请求有哪几种方式

cURL、file_get_contents、fopen、fsockopen

### http状态码

状态码 原因短语

- 1XX Informational （信息性状态码） 接收的请求正在处理
- 2XX Success （成功状态码） 请求正常处理完毕
- 3XX Redirection （重定向状态码) 需要进行附加操作以完成请求
- 4XX Client Error（客户端错误状态码） 服务器无法处理请求
- 5XX Server Error （服务器错误状态码) 服务器处理请求出错




