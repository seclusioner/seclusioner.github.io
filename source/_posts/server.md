---
title: Lab Server 租借&使用
date: 2025-01-01 03:39:06
tags:
- [Lab]
category: 
- [Lab]

description: 記錄server租借使用方式，若有錯誤麻煩告知，會陸續更新維護
cover: https://c4.wallpaperflare.com/wallpaper/851/501/292/programming-code-minimalism-wallpaper-preview.jpg
top_img: https://c4.wallpaperflare.com/wallpaper/851/501/292/programming-code-minimalism-wallpaper-preview.jpg
---

<body onload="SAONotify('Server租借方法', '請詳細參閱且實際操作，步驟不一定都是對的');"></body>

{% tip home %}
這裡會記錄租借server的方法，但請注意**步驟不一定完全正確，請隨時注意最後更新的時間**，還是須以當時管理server的人說的為主，或是直接請教正在使用的人
{% endtip %}

{% tip ban %}
這篇文章主要是給實驗室的人方便使用(因為我猜也沒多少人會來看我的網頁啦)，若有公開的問題或造成管理人的麻煩，不好意思再麻煩通知我，我馬上刪掉
{% endtip %}

## 前言
首先恭喜你進入我們實驗室，祝你好運~

這裡主要是文字為主，沒有圖文搭配，這一點比較抱歉，不過我相信各位可以的。

當初開發的學長其實已經有詳細把booking system pull到 Github 上了，後來的maintainer們創了一個公用的實驗室Github將該repo fork過來，可以自行觀看，若是maintainer則看越詳細越好。

{% link Lab Github, https://github.com/msplntustee/AIVC-Server-Booking, https://avatars.githubusercontent.com/u/215465283?v=4 %}

<br>

這邊會寫簡單的使用流程，過程**僅供參考**。

## Docker
在使用 GitHub 上的程式碼進行開發時，常會遇到環境相容性的問題。例如 PyTorch 和 CUDA 的版本對不上，導致程式無法順利執行；又或者當你完成開發並確認程式可正常運行後，換到另一台主機執行時，必須重新安裝所有相依的套件與工具，不僅耗時費力，還容易出現錯誤。

`Docker` 是一種輕量級的容器（container）技術，能夠將整個開發環境（包括作業系統、所需的套件、函式庫等）打包成一個可移植的映像檔（image）。這樣就能避免每次換環境都要重新安裝，確保專案在不同主機上也能有一致的執行結果。

{% image https://miro.medium.com/v2/resize:fit:1400/1*bcP-nlV1Z8geRV-AHA6O9g.png %}

舉例來說，在撰寫深度學習相關程式時，常常需要搭配特定版本的 CUDA、cuDNN 和 PyTorch，手動安裝過程既繁瑣又容易出錯。此時可以直接從 Docker Hub 下載與需求相符的官方映像檔，再透過撰寫 Dockerfile 客製化環境，快速建構一個可重現的開發空間。

那為甚麼我要在這邊提這個呢？因為從使用者（user）的角度出發，server的運作方式就是你以用戶身份遠端連線到某個 Host，並透過給定的 IP 和 Port 取得系統分配的container，這個container在build時會有預設的image，若要使用不同版本的image要跟maintainer說或是使用預設的幾個版本。

## 環境建置

這部分有需要再看就好，我會依照當初VIC學長交接的內容下去寫，若有需要PPT再跟我說(PPT有圖)

{% folding cyan, 察看環境建置 %}
以我自己為例，主機顯卡是`RTX 5080`(當時較新的)，OS是Win 11、x64
IDE：VScode
Python：我選的版本是`3.11.9`[傳送門](https://www.python.org/downloads/release/python-3119/)(因為有時候新版的會有一些相容性的問題)，可去[官網](https://www.python.org/downloads/)查詢，會有不同的Release version，當然後續虛擬環境上可以指定，或是用docker的image建

接著若要做AI，大致可分為：
## 安裝Anaconda
官網：https://www.anaconda.com/download/
現在要下載好像要註冊帳號，就弄一下後，會有兩個類型

## 安裝CUDA

## 安裝cuDNN


{% endfolding %}



## 顯卡指令

查看GPU相關資訊、driver的版本、CUDA版本等等，並與後續pytorch、cuDNN等版本做搭配
``` bash
nvidia-smi
```
{% tip warning %}
其他的指令可能需要額外安裝套件，例如{% kbd nvitop %}，請自行參閱查詢。
{% endtip %}

## Linux基本指令

ls: 查看目錄檔案
rm <filename> : 刪除某個檔案
mv <dir1> <dir2> : 將目錄1移動至目錄2
cd <path>: 打開/退出目錄

這部分我有點懶，有需要可以去查，大致上常用的就那些~

## 華夏server

### 租借方式
我以`Win10`為例，打開你的cmd，輸入：

``` bash
ssh booking@140.118.164.5X -p <port>
```

總共有5張顯卡，這裡的port就是ssh連線的port號，顯卡配置： (Jason學長筆，2024.09.配置)

{% kbd aivc01 %}（140.118.164.51）port:10000 –> 3090
<br>

{% kbd aivc02 %}（140.118.164.52）port:9999 –> A100
<br>

{% kbd aivc02 %}（140.118.164.52）port:10000–> 3090
<br>

{% kbd aivc03 %}（140.118.164.53）port:10000–> RTX 8000
<br>

{% kbd aivc04 %}（140.118.164.54）port:10000–> RTX 6000
<br>

<br>

{% tip warning %}
！！注意：這部分也是會變來變去，還是要自己去問比較好！！但我可能懶得改。
{% endtip %}

**租借command(挑其中一個)：**
``` bash
ssh booking@140.118.164.5X -p <port>
```

範例:
``` bash
ssh booking@140.118.164.53 -p 10000
```

server default passwords: {% psw aivc %}

進去後你會看到非常漂亮的大字：{% kbd AIVC %}

這時候你會看到像是linux的terminal`(booking@...$)`，就可以輸入command租借了。

查詢booking的情況:

``` bash
booking -ls
```

這時候你會看到你租借的訊息，在你的user_id後面會有一組port號（這裡則是docker給你的port號，跟前面的ssh port不同），是你之後要登入時需輸入的系統分配給你的container port。

租借指令：

``` bash
booking
```

輸入後就會進到booking畫面，第一次進去需輸入你的學號和你自己設定的密碼，輸入完成後會請你輸入租借時間(開始/結束)，只須按照指示的格式輸入即可~
租借格式：

起始時間：可以打`now`，或是按照上面指示
結束時間：可以打`2-day`、`2-week`等等，也可以中規中矩打標準格式

另外，若有特殊需求或是任何狀況請直接跟管理server的人（maintainer）討論，這樣最快，不然有時候model太大可能會需要較多的資源(尤其最近LLM案子越來越多

**租借後半小時才會刷新**

刷新後...

假設我租借的IP是53、port是12345，則cmd的輸入指令有更改：
``` bash
ssh root@140.118.164.53 -p 12345
```

若有問題就填Yes就好，

接著輸入你前面設定的密碼，一樣會顯示"AIVC"，就進到container了。

進入後你可以輸入

``` bash
ls
```

你會看到有三個資料夾 【Backup】、【Dataset】以及【Work】，**一切的工作(建環境、coding)等都要在Work這個目錄下**，不然server刷新後你的檔案就會消失囉（Work是預設的`WORKDIR`）。

### VScode設置與使用

- Remote SSH

VScode是常用拿來寫code的IDE之一。

首先要去VScode裡安裝Remote SSH模組，然後選擇連到host，接著輸入（範例）：

``` bash
ssh root@140.118.164.53 -p 12345
```
一樣輸入你設定的密碼，

接著打開【Work】的資料夾，於該目錄下建立環境。

虛擬環境除了`anaconda`，還有`pyenv`，但我主要是用`anaconda`，所以我只寫`anaconda`的部分，若有其他人想要加其他內容上去再跟我說一聲，可以寫好給我我再更新~


{% note info %}
**Note：** 其實booking system有預先裝好虛擬環境tool，但我目前是用anaconda，若要使用預設環境可以去上面寫的實驗室Github booking system repo查。
{% endnote %}

- Anaconda 建置

查看版本：https://repo.anaconda.com/archive/

首先進入bash：
``` bash
bash
```

1. 下載 Anaconda 安裝包：

``` bash
wget https://repo.anaconda.com/archive/Anaconda3-2024.02-1-Linux-x86_64.sh
```

若安裝包下載成功會出現下載訊息，若失敗或找不到檔案則會報錯 (Error 404)

2. 安裝 Anaconda：
注意：版本可能會隨著硬體設備更新而不同，因此還是要去上面的網址裡面找到比較新的版本，這邊以我當時的版本為主
``` bash
bash Anaconda3-2024.02-1-Linux-x86_64.sh
```
他會顯示 "Welcome to Anaconda3 ... "

接著就一直按Enter，直到他問你yes/no，輸入yes就對了。
然後就按Enter，系統就會自動安裝了。

{% tip warning %}
補：若要問你安裝路徑，應該要選擇Work的目錄下(直接輸入路徑即可，"root/Work/anaconda3")，不然下次刷新會需要重裝
{% endtip %}


安裝command一樣是：
``` bash
bash Anaconda3-2024.02-1-Linux-x86_64.sh
```

最後他會問 "You can undo this by running `conda init --reverse $SHELL`?"
我這邊輸入"no" --> 但他應該是要自動將anaconda3加入環境變數，所以應該是要選"yes"
安裝就結束了。

3. 重新加載 shell 設定（或重新啟動你的終端）

進入bash:
``` bash
bash
```
你會進入terminal (root@...#)

``` bash
source ~/.bashrc
```

這時候運行

``` bash
conda --version
```

如果你前面選no會報錯(如果有顯示版本表示沒有問題，你就可以跳過以下部分)，這是因為沒有將anaconda加到環境變數，因此你需要執行以下步驟：

確認 Anaconda 安裝目錄：

``` bash
ls ~/anaconda3
```
他會顯示許多檔案(anaconda安裝的檔案)，這時候檢查有沒有安裝成功：
``` bash
ls ~/anaconda3/bin/conda
```
Output:
/root/Work/anaconda3/bin/conda

表示剛剛確實有安裝成功，則可以直接輸入以下指令：
``` bash
echo 'export PATH="/root/Work/anaconda3/bin:$PATH"' >> ~/.bashrc
```

接著再輸入
``` bash
conda --version
```

即可看到conda版本。
補：
若沒進入conda，則再次輸入：
``` bash
source ~/.bashrc
```

若terminal前面多了`(base)`，表示成功進入anaconda的terminal，就可以開始開發了。

### tmux
若想要本地端關機後code一樣可以在server上跑，則可以使用tmux。

進入container後，於進入bash之前，可以輸入以下指令：

1. Start tmux session
自動編號：
``` bash
tmux
```
指定名稱 (session_name）：
``` bash
tmux new -s <session_name>
```

2. List session
可以使用此指令查看你剛剛創建的session：
``` bash
tmux ls
```

Rmk: 若出現error或是沒有該檔案/目錄，可以直接回到上面創建一個ne session再輸入，應該就會有了 (之前有base，但後來沒看到了)

3. Re-connect to session
連接到指定會話：
``` bash
tmux attach -t <session_name_or_number>
```
連接到最近的會話：
``` bash
tmux attach
```
補：`attach` 可以直接打 `a`

4. Close session
``` bash
exit
```
或是Ctrl + D

5. Delete session
刪除指定會話：
``` bash
tmux kill-session -t <session_name_or_number>
```
刪除所有會話：
``` bash
tmux kill-server
```

### FileZilla Client

若要傳輸相關檔案(例如dataset)，則需透過此軟體去做。

一開始連線會報錯，這是因為系統預設是FTP傳輸，但server系統是用SFTP，因此需先去設定站台

檔案 >> 站台管理員 >> 新增站台

更改協定為SFTP
輸入你借的主機：140.118.164.53 (假設)
使用者名稱：root
port: 12345 (前面分配的)
密碼：<你自己設定的>

接著就可以看到旁邊是你server裡面Work目錄下的檔案了，把你需要的檔案從local端(左側)拖到server(右側)即可。


## Server ssh 連不進去

出現以下情形：

``` bash
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that a host key has just been changed.
The fingerprint for the ECDSA key sent by the remote host is
SHA256:dIV67hEbVNQVU8J6Jr6VYc2amZI08xmsS7Y0QAZt7po.
Please contact your system administrator.
Add correct host key in C:\\Users\\seclu/.ssh/known_hosts to get rid of this message.
Offending ECDSA key in C:\\Users\\seclu/.ssh/known_hosts:3
ECDSA host key for [140.118.164.53]:10000 has changed and you have requested strict checking.
Host key verification failed.
```

Solution：去C:/Users/<username>/ >> 找到.ssh >> 有一個"known_hosts"的檔案，打開檔案刪掉記錄(**記得存檔**)，再連一次。

希望有幫助到各位~

若有錯誤或需要修正的地方，可以再評論或是直接聯絡我，或是問學長姊，如有更多需求請找maintainer詢問（但主要還是要靠自己，不要一有事情就找maintainer）。