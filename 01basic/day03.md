### 数据库基本操作：增改查删 ###
- 显示所有数据列表
	- show dbs
- *显示当前数据库对象或集合*（查看当前数据库名）
	- db
- 创建数据库或连接到一个指定的数据库
	- use DATABASE_NAME
	- 如果数据库不存在，则创建数据库，否则切换到指定数据库。
	- 创建的数据库并不在数据库的列表中， 要显示它，我们需要向数据库插入一些数据。
	- 在 MongoDB 中，集合只有在内容插入后才会创建! 就是说，创建集合(数据表)后要再插入一个文档(记录)，集合才会真正创建。

- 向数据库中，插入数据
	- db.DATABASE_NAME.insert(文档)
	- MongoDB 中默认的数据库为 test，如果你没有创建新的数据库，集合将存放在 test 数据库中。

示例：

	use lookon
	db
	show dbs
	db.lookon.insert({'name': 'Tom'})
	show dbs

- 删除数据库
	- db.dropDatabase()

示例：

	show dbs
	use lookon
	db
	db.dropDatabase()
	show dbs

