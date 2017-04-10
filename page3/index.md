## MongoDB安裝

### 準備
帶有sudo非root用戶的Debian 8服務器。您可以在使用Debian 8的初始服務器設置指南中設置具有這些權限的用戶

### 第1步– 安裝MongoDB

1.MongoDB已經包含在Debian的軟件包存儲庫中，但官方MongoDB存儲庫提供了最新的版本，是推薦的安裝軟件的方式。在這一步中，我們將把這個官方倉庫添加到我們的服務器。  

Debian通過驗證軟件包是否使用GPG密鑰進行簽名來確保軟件包的真實性，因此我們首先必須為官方MongoDB存儲庫導入它們的密鑰。  

```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6
```

2.我們必須添加MongoDB存儲庫詳細信息，因此apt將知道從哪裡下載軟件包。

發出以下命令為MongoDB創建列表文件(針對Debain 8)。

```
echo "deb http://repo.mongodb.org/apt/debian jessie/mongodb-org/3.4 main" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.4.list
```

3.更新套件內容
```
sudo apt-get update  
```

4.安裝 MongoDB 套件
```
sudo apt-get install -y mongodb-org
```

### 第二步- 執行MongoDB

1.執行MongoDB
```
sudo service mongod start
```
2.確認MonogoDB 已開啟  
檢視Log文件 /var/log/mongodb/mongod.log
```
[initandlisten] waiting for connections on port <port>
```
<port> 在 /etc/mongod.conf 裡做設定, 27017 是預設值.  

3.停止MongoDB
```
sudo service mongod stop
```  

4.重新啟動MongoDB
```
sudo service mongod restart
```  

5.開始使用MongoDB
[MongoDB 官方文檔位置](https://docs.mongodb.com/master/#getting-started)  


### 解除安裝  

停止MongoDB
```
sudo service mongod stop
```  

移除套件
```
sudo apt-get purge mongodb-org*
```  

移除資料庫以及log檔
```
sudo rm -r /var/log/mongodb
sudo rm -r /var/lib/mongodb
```

```
