### MongoDB简介 ###
- NoSQL（Not Only SQL）数据库分类类型：文档存储
- CP：满足一致性，分区容忍性的系统，通常性能不是特别高

MongoDB 是由C++语言编写的，是一个**基于分布式文件存储的开源数据库系统**。

在高负载的情况下，添加更多的节点，可以保证服务器性能。

MongoDB 旨在为**WEB应用**提供可扩展的高性能数据存储解决方案。

MongoDB 将**数据存储为一个文档，数据结构由键值(key=>value)对组成**。MongoDB 文档类似于 JSON 对象。字段值可以包含其他文档，数组及文档数组。

一个mongodb中可以建立多个数据库。

MongoDB的默认数据库为"db"，该数据库存储在data目录中。

*MongoDB的单个实例可以容纳多个独立的数据库，每一个都有自己的集合和权限，不同的数据库也放置在不同的文件中*。

数据库通过名字来标识。

- 数据库名可以是满足以下条件的任意UTF-8字符串。
	- 不能是空字符串（"")。
	- 不得含有' '（空格)、.、$、/、\和\0 (空字符)。
	- 应全部小写。
	- 最多64字节。

- 特殊作用数据库
	- admin： 从权限的角度来看，这是"root"数据库。要是将一个用户添加到这个数据库，这个用户自动继承所有数据库的**权限**。一些特定的服务器端命令也只能从这个数据库运行，比如列出所有的数据库或者关闭服务器。
	- local: *这个数据永远不会被复制*，可以用来存储限于**本地单台服务器**的任意集合。
	- config: 当Mongo用于分片设置时，config数据库在内部使用，用于保存**分片**的相关信息。

### 安装与运行 ###
- 安装MongoDB
	- 选择定制安装路径，一路默认，等着30多分钟的安装过程，重启电脑。
	- 安装过程中，在data目录后添加db

- dos运行
	- d:
	- cd D:\Program Files\MongoDB\Server\4.2\bin
	- mongo

- 退出
	- exit
