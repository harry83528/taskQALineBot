## 檔案說明
    本專案用flask搭配Heroku伺服器部屬https web server,再用 /callback post路徑和line bot 做串接,以下為檔案說明
    Procfile:宣告多種程序的類型（執行的程式種類）的檔案
    app.py:主程式
    config.ini:設定檔
    function.py:自定義函數檔
    requirements.txt:已安裝模組名稱,根據 requirements.txt 列表安裝模組
    runtime.txt:告知python版本
    nlp資料夾:存放介接威聖電子股份有限公司API的檔案
    fileTemplates資料夾:存放word模板
    fileOutput資料夾:存放輸出檔案
    templates資料夾:存放html模板
    static資料夾:存放靜態檔案css、js等
## 建置步驟1(申請Heroku帳號):
    因為使用Heroku平台,所以要先到Heroku網站建立帳號
    Heroku網址:<https://dashboard.heroku.com/>
## 建置步驟2(創建Heroku APP):
    heroku登入後首頁new>create new app 依照網頁步驟建置您自己的APP,並記住您自己的App名稱
## 建置步驟3(建立Line bot):
    到Line開發者網站建置Line bot
    網址:https://developers.line.biz/en/
    Line帳號登入> Providers>Create創造提供者
    Channel >Create a channel> Messaging API>依據欄位填值創出一個Bot
    Webhook settings 狀態打開
    並查出以下資訊
*  Channel ID
*  Channel secret(沒有的話點選Issue)
*  token
*  Webhook URL(https://{Heroku_app_name}.herokuapp.com/callback)
*  Basic ID
## 建置步驟4(下載版更程式):
    安裝 Git與Heroku CLI
    Git:
    https://backlog.com/git-tutorial/tw/intro/intro2_1.html
    Heroku CLI:
    https://devcenter.heroku.com/articles/heroku-cli#windows
    然後點 64-bit 下載安裝檔，下載後點開。
## 建置步驟5(版更指令):
    下載本git專案到您的電腦,假設您下載路徑為D:\webapps\taskbot\
    安裝好後cmd Cd到上傳資料夾(專案資料夾)，並打以下指令
    D:\webapps\taskbot>
    $ heroku login
    $ git init
    $ heroku git:remote -a "Heroku APP名稱"
    上述步驟版更第一次才要做，當之後程式有修改，重做下列3個步驟就好
    $ git add .
    $ git commit -m "版更敘述文字"
    $ git push heroku master
    如果要重新clone下來的步驟:
    $ heroku login
    $ heroku git:clone -a "Heroku APP名稱"
    $ cd "Heroku APP名稱"
    錯誤想看log:
    $ heroku logs --tail
## 建置步驟6(Line Managerg刪除自動回覆機制):
    最後再到Line Manager頁面將Auto reply message資料全部刪除，這樣才可以將使用者送的訊息透過python後台處理，回丟訊息給使用者。
![image](https://github.com/harry83528/taskQALineBot/blob/master/messageImage_1578626946104.jpg)


