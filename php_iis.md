# Windows10 配置 PHP7 與 IIS 環境

## 安裝PHP
<p>下載網址: <a href="https://www.php.net/downloads.php">https://www.php.net/downloads.php</a></p>
![image](https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_1.png)
<p>進入Windows downloads挑選符合環境的.zip下載下來<br>
解壓縮放於C槽目錄底下<br>
接著進去控制台>系統及安全性>系統，左邊選單點選"進階系統設定"裡面的環境變數</p>
![image](https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_2.png)
<p>系統變數>Path將放在C槽的PHP給設定進去</p>
![image](https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_3.png)
<p>回到C:\php裡面，從php.ini-development這個預設提供的參照檔案複製出來<br>
重新命名為php.ini，此為PHP未來執行會需要的執行檔</p>
![image](https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_4.png)
<p>最後打開命令提示字元，輸入php -v<br>
可以發現已經能成功執行PHP囉</p>
![image](https://github.com/JackyChenXD/Tech-Article/blob/master/images/image_5.png)
