## MongoDB 基本 CRUD(新增、讀取、更新、刪除) 使用

### 新增  

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
概念如下:  

![img](https://donaldsher.github.io/LearningBlog/page4/0.png)

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

操作截圖  

![img](https://donaldsher.github.io/LearningBlog/page4/1.png)  

3.2版本 增加Function

新增單筆並檢視資料  
```
db.mydbCollection.insertOne({Name:"Amy",Age:"32"})
```  

新增多筆並檢視資料  
```
db.mydbCollection.insertMany([{Name:"Amy",Age:"32"},{Name:"Chris",Age:"29"}])
```  

操作截圖  
![img](https://donaldsher.github.io/LearningBlog/page4/2.png)  


### 讀取  

讀取剛剛集合理的所有文件(沒有設判斷)
```
db.mydbCollection.find()
```  

讀取文件內名稱是Amy的文件
```
db.mydbCollection.find({Name:"Amy"})
```  

操作截圖
![img](https://donaldsher.github.io/LearningBlog/page4/3.png)


可以使用比較語句來找讀取指定的文件  

$eq 匹配指定值的值  
```
```

$gt 匹配比指定值更大的值
```
```  

$gte 匹配大於或等於指定值的值
```
```

$lt 匹配小於指定值的值  
```
```  

$lte 匹配小於或等於指定值的值  
```
```  

$ne 匹配不等於指定值得所有值
```
```  

$in  匹配指定陣列中規定的值的所有值
```
```

$nin 匹配沒有在指定陣列中規定的值得所有值
```
```  






[跳至首頁](https://donaldsher.github.io/LearningBlog/)
