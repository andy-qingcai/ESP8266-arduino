## 关于WIFIClient库的使用教程

WIFIClient是一个实现建立TCP连接的库，具体放在**WIFIClient.h**中

~~~C
#include"WIFIClient.h"
WiFiClient client;
~~~

具体的操作对象为WIFIClient，这里先实体化这个对象，方便下面演示

库中主要有以下函数：

1. connect
2. connected
3. write
4. print
5. println
6. available
7. read
8. flush
9. stop

### connect()

用来让客户端连接服务器的函数

~~~c
client.connect(ip, port)
client.connect(URL, port)
~~~

ip : 填入一个4字节的数组，推荐unsigned char [4]

URL : 填入服务器的URL

port : 填入对应连接服务器的端口

### connected()

已经连接到服务器返回true，否则返回0

~~~C
client.connected()
~~~

### write()

向已经连接的服务器发送数据(一个字节)

~~~C
client.write()
~~~

### print()

向服务器发送一组数据

~~~C
client.print(data,BASE)
~~~

data : 要发送的数据

BASE( 可选 ) : 

​			`DEC`: 转换成10进制

​			`OCT`: 转换成8进制

​			`HEX`: 转换成16进制

### println()

同print(),区别在于会在发送的数据最后加上换行符

~~~C
client.println(data,BASE)
~~~

### available()

返回当前可读取的数据长度( 字节 )

~~~C
client.available()
~~~

### read()

读取一个字节，并使得available()返回的值减一

~~~C
client.read()
~~~

### flush()

删除还未读取的所有字节

~~~C
client.flush()
~~~

### stop()

停止与服务器的连接

~~~C
c
~~~

