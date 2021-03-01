# Windows10 配置 PHP7 與 IIS 環境

## 安裝 PHP
<p>下載網址: <a href="https://www.php.net/downloads.php">https://www.php.net/downloads.php</a></p>
<img src="https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_1.png">
<p>進入Windows downloads挑選符合環境的.zip下載下來<br>
解壓縮放於C槽目錄底下<br>
接著進去控制台>系統及安全性>系統，左邊選單點選"進階系統設定"裡面的環境變數</p>
<img src="https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_2.png">
<p>系統變數>Path將放在C槽的PHP給設定進去</p>
<img src="https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_3.png">
<p>回到C:\php裡面，從php.ini-development這個預設提供的參照檔案複製出來<br>
重新命名為php.ini，此為PHP未來執行會需要的執行檔<br>
裡面可以調整資料庫連接或是檔案上傳大小限制等等的參數</p>
<img src="https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_4.png">
<p>最後打開命令提示字元，輸入php -v<br>
可以發現已經能成功執行PHP囉</p>
<img src="https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_5.png">

## 安裝 Visual Studio 2015 的 Visual C++ 可轉散發套件
<p>下載網址: <a href="https://www.microsoft.com/zh-TW/download/details.aspx?id=48145">https://www.microsoft.com/zh-TW/download/details.aspx?id=48145</a></p>
<img src="https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_6.png">

## 安裝 IIS 並啟用 CGI 模組
<p>控制台>程式和功能>開啟或關閉Window的功能</p>
<img src="https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_7.png">
<p>Internet Information Services > World Wide Web服務 > 應用程式開發功能<br>
將CGI打勾</p>
<img src="https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_8.png">
<p>在配置IIS前，先下載PHP MANAGER管理CGI的工具<br>
網址: <a href="https://www.iis.net/downloads/community/2018/05/php-manager-150-for-iis-10">https://www.iis.net/downloads/community/2018/05/php-manager-150-for-iis-10</a><br>
搜尋IIS，開啟Internet Information Services (IIS)管理員</p>
<img src="https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_9.png">
<p>點選PHP MANAGER進去，再點選Register new PHP version，輸入php裡面的php-cgi.exe路徑</p>
<img src="https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_10.png">
<p>設定完回到管理首頁點選"處理函式對應"，可以發現PHP已經設定好了</p>
<img src="https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_11.png">
<p>回到管理頁面點選"預設文件"，裡面可設定輸入http://localhost會導向的預設PHP檔案，<br>
IIS會依序去尋找對應檔案回傳結果</p>
<img src="https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_12.png">
<p>我們可以在C:\inetpub\wwwroot裡面新增一個index.php，裡面打上phpinfo();做測試<br>
最後在瀏覽器打上<a href="http://localhost">http://localhost</a>，會看到顯示出PHP當下版本，就是設定成功囉</p>
<img src="https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_13.png">

## 新增站台

<p>在D:\新增如上的index.php檔案</p>
<img src="https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_14.png">
<p>回到IIS管理頁面，左側選單"站台"，右鍵點選新增網站</p>
<img src="https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_15.png">
<p實體路徑打IIS要指向的檔案路徑，繫結則可設定哪些IP網址要指向過去<br>
若有申請實體IP，這邊可以直接填上，我們這邊用本機網址來做測試<br>
輸入<a href="http://127.0.0.1:8080">http://127.0.0.1:8080/</a>，就會出現index.php的結果代表成功囉<br>
若有多個IP，可以在控制台首頁右方選單，編輯站台>繫結，輸了多個IP去指向該檔案路徑喔</p>
<img src="https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_16.png">
