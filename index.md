## MongoDB介紹

Mongo的資料體結構是以 Key,Value組合的，儲存的方式與Json格式完全相同，另外多了很多的靈活性，也就每一筆文件的是欄位的型態是不一定的，欄位的存在性也是不一定的。如果你學過Relation DataBase一定會很困惑，因為MSSQL、MySQL教我們要先設定Table Schema後，明確定義Table的Column和其型態，有利於資料整理、資料存儲、並執行正規化的行為…等。

但在文本資料庫並沒有這樣子的限制，不過我認為雖然有這樣的彈性還是乖一點用Relation DataBase的設定概念來設計你的MongoDB資料庫。不然有一天一定天下大亂的。

### Monogo特色
1.MongoDB可以處理資料庫為 T級量 的資料庫，也就是處理大數據的資料庫。
2.分散式的資料庫模式，可以把眾多資料庫串聯後處理大數的資料。

### MongoDB的基本術語我們與Relation DataBase術語對照說明
Relation DataBase                       MongoDB
--------------------------------------------------------------------------
資料庫(Database)                         DataBase
資料表(Table)                            Collection
資料(Record/Row)                         Document
欄位(Column)                             Field
主索引(PK)                               _id_
function                                function ( )
stored procedure                        mapreduce
--------------------------------------------------------------------------


### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/donaldsher/blog/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
