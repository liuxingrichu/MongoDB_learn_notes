### 文档基本操作：增查 ###
个人理解：文档相当于关系数据库里面的记录。

文档的数据结构和 JSON 基本一样。

所有存储在集合中的数据都是 BSON 格式。

BSON 是一种类似 JSON 的二进制形式的存储格式，是 Binary JSON 的简称。

- 插入文档
	- db.COLLECTION_NAME.insert(document)
	- MongoDB 使用 insert() 或 save() 方法向集合中插入文档。
	- 插入文档你也可以使用 db.col.save(document) 命令。如果不指定 _id 字段 save() 方法类似于 insert() 方法。如果指定 _id 字段，则会更新该 _id 的数据。

- 查看文档
	- db.col.find()

示范：

	show dbs
	use lookon
	db
	show tables

	方式一：
	db.col.insert({title: 'MongoDB 教程', 
	    description: 'MongoDB 是一个 Nosql 数据库',
	    by: '菜鸟教程',
	    url: 'http://www.runoob.com',
	    tags: ['mongodb', 'database', 'NoSQL'],
	    likes: 100
	})
	show tables
	db.col.find()

	方式二：将数据定义为一个变量
	document=({title: 'MongoDB 教程', 
	    description: 'MongoDB 是一个 Nosql 数据库',
	    by: '菜鸟教程',
	    url: 'http://www.runoob.com',
	    tags: ['mongodb', 'database', 'NoSQL'],
	    likes: 100
	});
	
	db.col.insert(document)
	db.col.find()


以上实例中 col 是我们的集合名，如果该集合不在该数据库中， MongoDB 会自动创建该集合并插入文档。
