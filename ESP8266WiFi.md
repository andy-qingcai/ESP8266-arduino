## 使用教程

 ESP8266内所有的关于WIFI的函数都在**ESP8266WIFI.h **内，首先亮出[官方教程][https://arduino-esp8266.readthedocs.io/en/latest/esp8266wifi/station-class.html#config]

~~~C
#include"ESP8266WIFI.h"
~~~

内含有(我也不知道里面有什么，一堆class继承class的，等我看玩源码在写)，这篇教程仅写出内部主要的几个函数的使用方法。

关于WIFI的基本操作时通过一个名为WIFI的实体来完成的( 不需要额外声明WIFI对象 )，如

~~~C
WIFI.begin(ssid,password)
//表示打开连接到名字为ssid，密码是passwor的wifi
~~~

主要有以下函数(有一些并不是那么常用，没有列出)，分类下来分别是

1. 关于连接和配置的函数
   + begin
   + mode
   + config
   
2. 关于管理连接的函数
   + reconnect
   + disconnect
   + isConnected
   + waitForConnectResult
   
3. 关于网络配置的函数

   + macAddress

   - localIP
   - subnetMask
   - gatewayIP

## 关于连接和配置的函数

### begin()

启用并连接WIFI

~~~C
WiFi.begin(ssid, password)
~~~

ssid : 要连接的WIFI的名称

password : 要连接WIFI的密码

### mode()

设定WIFI的类型

~~~C
WIFI.mode(WiFiMode_t m)
~~~

WiFiMode_t :  

- `WIFI_OFF`: 关闭wifi
- `WIFI_STA`: 启动STA模式( 连接wifi )
- `WIFI_AP`: 启动AP模式( 开启热点 )
- `WIFI_AP_STA`: 同时开启STA和AP模式

### config()

配置基本的网络设定

~~~C
WiFi.config(local_ip, gateway, subnet, dns1, dns2)
~~~

local_ip : 选定ESP8266的ip地址

gateway : 选定所连接WIFI的网关

subnet : 选定电子掩码

dns : 选择DNS服务器位置

## 关于管理连接的函数

### reconnect()

断开所连接的WIFI并重新连接 , 重新连接成功返回true，否则返回false

~~~C
WiFi.reconnect()
~~~

### disconnect()

断开所连接的WIFI

```C
WiFi.disconnect()
```

### isConnected()

判断WIFI是否连接成功，连接成功返回true，否则返回false

```C
WiFi.isConnected()
```

## 关于网络配置的函数

### macAddress()

返回ESP8266的mac地址

```
WiFi.macAddress(mac)
```

mac : 是一个unsigned int类型的长度为6的数组，返回的mac地址放入这个变量中

### localIP()

返回ESP8266的IP地址，其中返回值是IPAddress类型的

```
WiFi.localIP()
```

### subnetMask()

返回ESP8266的电子掩码

```
WiFi.subnetMask()
```

### gatewayIP

返回ESP8266的网关

```
WiFi.gatewayIP()
```

