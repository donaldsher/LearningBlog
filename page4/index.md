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

![img](https://donaldsher.github.io/LearningBlog/page4/0.jpg)

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

**3.2版本 增加Function**

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


可以使用比較語句來找讀取指定的資料(文件 document)  

**$eq**  

Equality(匹配指定值的值的資料)
```
db.mydbCollection.find({Name:{$eq:"Amy"}})
```  
結果就會跟上面的 `db.mydbCollection.find({Name:"Amy"})`  一樣  找到Name的值是Amy的資料

![img](https://donaldsher.github.io/LearningBlog/page4/4.png)


**$gt**  

Greater Than(匹配比指定值更大的值的資料)
```
db.mydbCollection.find({Age:{$gt:"24"}})
```  

**$gte**  

Greater Than Equals(匹配大於或等於指定值的資料)
```
db.mydbCollection.find({Age:{$gte:"32"}})
```

**$lt**  

Less Than(匹配小於指定值的資料)  
```
db.mydbCollection.find({Age:{$lt:"30"}})
```  

**$lte**  

Less Than Equals(匹配小於或等於指定值的所有資料)  
```
db.mydbCollection.find({Age:{$gt:"29"}})
```  

**$ne**  

Not Equals(匹配不等於指定值的所有資料)
```
db.mydbCollection.find({Age:{$ne:"29"}})
```  

結果  

![img](https://donaldsher.github.io/LearningBlog/page4/5.png)

**$in**  

匹配在陣列中的值
```
db.mydbCollection.find({Name:{$in:["Amy","Chris"]}})
```

**$nin**  

Not In(匹配沒有在陣列中的值)
```
db.mydbCollection.find({Name:{$nin:["Amy","Chris"]}})
```  

結果  

![img](https://donaldsher.github.io/LearningBlog/page4/6.png)


也可以利用pretty() 這個Function 讓資料檢視比較易閱讀  
```
db.mydbCollection.find({Name:{$nin:["Amy","Chris"]}}).pretty()
```  

![img](https://donaldsher.github.io/LearningBlog/page4/7.png)

**$and**  

and運算元  以下範例讀取 匹配含有兩個鍵值(key與value)的所有資料
```
db.mydbCollection.find({$and:[{"Name":"Amy"},{"Age":"32"}]}).pretty()
```  

![img](https://donaldsher.github.io/LearningBlog/page4/8.png)  


**$or**  

or運算元 以下範例讀取 匹配含有兩個其中之一的鍵值(key與value)的資料
```
db.mydbCollection.find({$or:[{"Name":"Seteve"},{"Name":"Amy"}]})
```    


![img](https://donaldsher.github.io/LearningBlog/page4/9.png)





### 更新  

更新的Function 主要是 Update()與Save()  

**Update()**

利用Update() 將匹配到Name含有Seteve或Amy的文件 更新Age的值為50
```
db.mydbCollection.update({$or:[{"Name":"Seteve"},{"Name":"Amy"}]},{$set:{"Age":50}},{multi:true})
```  

結果  

![img](https://donaldsher.github.io/LearningBlog/page4/10.png)  

搭配前面的讀取語句  

![img](https://donaldsher.github.io/LearningBlog/page4/11.png)


**Save()**

利用_id索引 直接替換資料文件  

將_id索引值為`58ecb8113bdd158ca3dddcf0` 的文件替換成 `{Name:"Lisa",Age:20}`
```
db.mydbCollection.save({"_id":ObjectId("58ecb8113bdd158ca3dddcf0"),"Name":"Lisa","Age":20})
```

結果  

![img](https://donaldsher.github.io/LearningBlog/page4/12.png)  

查詢  

![img](https://donaldsher.github.io/LearningBlog/page4/13.png)


### 刪除  

**Remove()**

將_id索引值為`58ecb8113bdd158ca3dddcf0` 的文件 刪除
```
db.mydbCollection.remove({"_id":ObjectId("58ecb8113bdd158ca3dddcf0")})
```  
結果

![img](https://donaldsher.github.io/LearningBlog/page4/14.png)


移除搜索到的第一筆資料  範例是移除第一筆 Age欄位是50的資料
```
db.mydbCollection.remove({Age:{$eq:50}},1)
```  
結果  

![img](https://donaldsher.github.io/LearningBlog/page4/15.png)





[跳至首頁](https://donaldsher.github.io/LearningBlog/)
