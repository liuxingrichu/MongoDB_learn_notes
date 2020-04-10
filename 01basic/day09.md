### MongoDB 条件操作符 ###
条件操作符用于比较两个表达式并从mongoDB集合中获取数据。

MongoDB中条件操作符有：

	(>) 大于 - $gt
	(<) 小于 - $lt
	(>=) 大于等于 - $gte
	(<= ) 小于等于 - $lte

实例：

	show dbs
	db
	use lookon
	db
	show tables
	db.col.find().pretty()
	db.col.remove({})
	db.col.find()
	db.col.insert({
	    title: 'PHP 教程', 
	    description: 'PHP 是一种创建动态交互性站点的强有力的服务器端脚本语言。',
	    by: '菜鸟教程',
	    url: 'http://www.runoob.com',
	    tags: ['php'],
	    likes: 200
	})
	db.col.insert({title: 'Java 教程', 
	    description: 'Java 是由Sun Microsystems公司于1995年5月推出的高级程序设计语言。',
	    by: '菜鸟教程',
	    url: 'http://www.runoob.com',
	    tags: ['java'],
	    likes: 150
	})
	db.col.insert({title: 'MongoDB 教程', 
	    description: 'MongoDB 是一个 Nosql 数据库',
	    by: '菜鸟教程',
	    url: 'http://www.runoob.com',
	    tags: ['mongodb'],
	    likes: 100
	})
	db.col.find()

#### MongoDB (>) 大于操作符 - $gt ####

db.col.find({likes : {$gt : 100}})

类似于SQL语句：

Select * from col where likes > 100;

#### MongoDB（>=）大于等于操作符 - $gte ####
db.col.find({likes : {$gte : 100}})

类似于SQL语句：

Select * from col where likes >=100;

#### MongoDB (<) 小于操作符 - $lt ####
db.col.find({likes : {$lt : 150}})

类似于SQL语句：

Select * from col where likes < 150;

#### MongoDB (<=) 小于等于操作符 - $lte ####

db.col.find({likes : {$lte : 150}})

类似于SQL语句：

Select * from col where likes <= 150;

#### MongoDB 使用 (<) 和 (>) 查询 - $lt 和 $gt ####

db.col.find({likes : {$lt :200, $gt : 100}})

类似于SQL语句：

Select * from col where likes>100 AND  likes<200;

#### 模糊查询 ####
查询 title 包含"J"字的文档：

	db.col.find({title:/J/})

查询 title 字段以"J"字开头的文档：

	db.col.find({title:/^J/})

查询 titl e字段以"程"字结尾的文档：

	db.col.find({title:/程$/}))