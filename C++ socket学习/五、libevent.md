# libevent
>libevebts是一个框架，封装了epoll，只需要调用接口即可

### 一、libevent的步骤
* 1.1 事件的底层处理框架
   * 一个函数
2. 消息循环
   * 一个函数
3. 创建事件
   * 不带缓冲区 - evnet
   * 带缓冲区  - bufferevent
4. 资源释放
    * 几个函数
    
### 二、libevent的安装 
* 2.1. libevent的作用:开源的库，提高开发效率
   * 封装了socket通信
   * 封装了I/O多路转接
   * 专注于网络，性能高
   * 事件驱动
* 2.2 libevent的安装 （源码安装）
   *  ./configure        : 检测环境，沈城makefile 
   *  make               : 编译源代码，生成一些库（动态/静态0或者一些）可执行程序
   *  sduo make install  : 做数据的拷贝到相应的目录
3. libevent 库的使用
   * 编译程序的时候指定 -levent即可 
   * 常用的头文件
   ```c
   #include <event2/event.h>
   #include <event2/listener.h>
   ```
### 3.1
   
   
     
   
  
