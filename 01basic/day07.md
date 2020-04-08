### 文档基本操作：删 ###

MongoDB remove()函数是用来**移除集合中的数据**。

在执行remove()函数前先执行find()命令来判断执行的条件是否正确，这是一个比较好的习惯。

#### remove() 方法（官网：不推荐） ####

remove() 方法的基本语法格式如下所示：

	db.collection.remove(
	   <query>,
	   <justOne>
	)

参数说明：

	query :（可选）删除的文档的条件。
	justOne : （可选）如果设为 true 或 1，则只删除一个文档，如果不设置该参数，或使用默认值 false，则删除所有匹配条件的文档。

实例：

	show dbs
	use lookon
	db
	show tables
	db.col.find().pretty()

	删除所有满足条件的文档
	db.col.remove({'title':'MongoDB save'})
	db.col.find()

	db.col.insert({title: 'MongoDB 教程', 
	    description: 'MongoDB 是一个 Nosql 数据库',
	    by: '菜鸟教程',
	    url: 'http://www.runoob.com',
	    tags: ['mongodb', 'database', 'NoSQL'],
	    likes: 100
	})
	db.col.insert({title: 'MongoDB 教程', 
	    description: 'MongoDB 是一个 Nosql 数据库',
	    by: '菜鸟教程',
	    url: 'http://www.runoob.com',
	    tags: ['mongodb', 'database', 'NoSQL'],
	    likes: 100
	})
	db.col.find().pretty()

	仅删除满足条件的一条文档
	db.col.remove({'title': 'MongoDB 教程'}, 1)
	db.col.find().pretty()

	删除集合中的所有数据
	db.col.remove({})
	db.col.find()

### deleteOne()和deleteMany() 方法（官网：推荐） ###

实例：

	仅删除满足条件的一条文档
	db.col.deleteOne({"title": "MongoDB 教程"})
	删除所有满足条件的文档
	db.col.deleteMany({"title": "MongoDB 教程"})
	删除集合中的所有数据
	db.col.deleteMany({})