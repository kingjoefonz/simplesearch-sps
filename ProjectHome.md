simplesearch是在linux平台下使用c/c++开发，专为PHP开发人员而研发的一款搜索引擎，其基于Xapian开发，目标是让所有PHP开发人员都很容易解决百万级数量以上的全文检索需求。

它的实现真的很简单。轻轻松松就能实现全文检索需求，它的整个过程就像你操作mysql一样简单。

## 主要特点 ##

  1. 快速：体积小，加载速度快，开发快
  1. 开源：开放源代码，高水平，高品质
  1. 底层：采用Xapian
  1. 并发：并用epoll模型，高并发
  1. 建索引速度：500条记录/s (机器配置为：4核xeon 3.0CPU 2G内存)
  1. 搜索速度：2百万条记录，搜索平均时间为:0.037S
  1. 可以随意更新记录，删除记录，比sphinx更加灵活





## 安装 ##
  1. ./configure --prefix=/opt/simplesearch/
  1. make && make install
  1. cd /opt/simplesearch/
  1. 启动:./sbin/simplesearch
  1. 停止：./sbin/simplesearch -s stop
  1. 将启动2个端口，请在iptables添加,并设置只有ip为：183.63.2.211(你自己的ip)  才能调用该接口，以确保安全性

```
-A RH-Firewall-1-INPUT -p tcp -m state --state NEW -m tcp --dport 6162 -s 183.63.2.211 -j ACCEPT
-A RH-Firewall-1-INPUT -p tcp -m state --state NEW -m tcp --dport 6163 -s 183.63.2.211 -j ACCEPT
```


  * 接口说明:http://blog.csdn.net/zll_liang/article/details/8283741
  * 创建检索库:http://blog.csdn.net/zll_liang/article/details/8283753
  * 搜索:http://blog.csdn.net/zll_liang/article/details/8283756
  * 添加数据:http://blog.csdn.net/zll_liang/article/details/8283750