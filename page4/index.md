## MongoDB 基本 CRUD(新增、修改、查詢、刪除) 使用

### 創建  

切換到叫mydb的db  
```
use mydb
```  

目前的db
```
db
```

在mydb(當前db)中的mydbCollection集合中插入一個文件(json)，沒有此集合便會產生一個叫myCollection的集合
```
db.mydbCollection.insert({Name:"Chris",Age:"32",Tel:"+891 335971"})
```

檢視mydbCollection集合內的文件數量
```
db.mydbCollection.count()
```

檢視資料庫中的所有db
```
show dbs
```

檢視mydb(當前db)中的所有集合
```
show collections
```  

操作示範  

![img](https://donaldsher.github.io/LearningBlog/page4/1.png)

[跳至首頁](https://donaldsher.github.io/LearningBlog/)
