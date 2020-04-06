### 集合基本操作：增查删 ###
集合，类似数据库中的表。

- 创建集合
	- db.createCollection(name, options)
	- 参数
		- name: 要创建的集合名称
		- options: 可选参数, 指定有关内存大小及索引的选项
	- 在MongoDB中，不需要创建集合。当你插入一些文档时，MongoDB 会自动创建集合。

- 查看集合
	- show collections
	- 或 show tables

- 删除集合
	- db.collection.drop()
	- 如果成功删除选定集合，则 drop() 方法返回 true，否则返回 false。

示例：

	use lookon
	db
	show dbs
	show tables
	db.createCollection("look")
	show tables
	show dbs
	db.look.drop()
	show tables
	show dbs
