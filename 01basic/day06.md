### 文档基本操作：改 ###

MongoDB 使用 update() 和 save() 方法来更新集合中的文档。

#### update() 方法 ####

update() 方法用于**更新已存在的文档**。语法格式如下：

	db.collection.update(
	   <query>,
	   <update>,
	   {
	     upsert: <boolean>,
	     multi: <boolean>,
	     writeConcern: <document>
	   }
	)

参数说明：

	query : update的查询条件，类似sql update查询内where后面的。
	update : update的对象和一些更新的操作符（如$,$inc...）等，也可以理解为sql update查询内set后面的
	upsert : 可选，这个参数的意思是，如果不存在update的记录，是否插入objNew,true为插入，默认是false，不插入。
	multi : 可选，mongodb 默认是false,只更新找到的第一条记录，如果这个参数为true,就把按条件查出来多条记录全部更新。
	writeConcern :可选，抛出异常的级别。

示范：

	db.col.update({'title':'MongoDB 教程'},{$set:{'title':'MongoDB'}})
	db.col.find().pretty()

以上语句只会修改第一条发现的文档，如果你要修改多条相同的文档，则需要设置 multi 参数为 true。

	db.col.update({'title':'MongoDB 教程'},{$set:{'title':'MongoDB'}},{multi:true})

#### save() 方法 ####
save() 方法通过传入的文档来替换已有文档。语法格式如下：

	db.collection.save(
	   <document>,
	   {
	     writeConcern: <document>
	   }
	)

参数说明：

	document : 文档数据。
	writeConcern :可选，抛出异常的级别。

实例：

	db.col.save({
	    "_id" : ObjectId("5e8a9514a0ca9094983e351d"),
	    "title" : "MongoDB save",
	    "description" : "MongoDB 是一个 Nosql 数据库",
	    "by" : "save",
	    "url" : "http://www.runoob.com",
	    "tags" : [
	            "mongodb",
	            "NoSQL"
	    ],
	    "likes" : 110
	})
	db.col.find().pretty()