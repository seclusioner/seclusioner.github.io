---
title: Adventure X Beginning
date: 2023-02-12 23:59:59
sticky: 9
tags: 
- [Level]
category:
- [Level]
description: Level 0
cover: https://i.pinimg.com/originals/44/ae/e4/44aee48a8e76e8080d93e995e8b1282a.jpg
top_img: https://i.pinimg.com/originals/44/ae/e4/44aee48a8e76e8080d93e995e8b1282a.jpg
swiper_index: 2
---

<body onload="SAONotify('Adventure X Beginning','GAME STAAAAAART！！！')"></body>

<!-- 1551 -->

# 前言

<font size="4">

雖然我覺得應該沒多少人會點進來，如果是我認識的點進來，可以跟我說一聲，我會很感謝你的！！！ <br>

像是冒險一樣，網頁上的密室逃脫？總之，就是解謎就對了，會先以闖關的形式呈現，之後會看再加入甚麼元素，在闖關的過程你會知道關於我的一些事情，或是一些我的心路歷程，當然有一兩關純粹是要讓你頭疼的。 <br>

本來寫了一些比較精緻的畫面，但不知道為啥沒辦法運行，之後有時間會持續改或是做的更精緻。 <br>

如果你真的有興趣，那就接著看下去吧！(ง๑ •̀_•́)ง  <br><br>


<!-- more -->


首先，感謝你點進來。( ￣□￣)/ 敬禮!! <(￣ㄧ￣ ) <(￣ㄧ￣ )<(￣ㄧ￣ ) <br>

找到正確的密碼(目前除了最後一關其餘皆為**四位數**)，便可進入下一關，當到最後一關，如果你能夠把所有關卡破完，你就可以前往我的主頁。<br>

之後有時間及靈感會陸續把東西加進來，會持續更新～～ ٩(๑❛ᴗ❛๑)۶ <br><br>

如果你成功的話，會自動將你帶到以下畫面：<br>

{% image https://i.pinimg.com/originals/f5/1e/66/f51e66abd0aba2d6140f6dd5421f89b3.png, alt=D.S.的主要網頁，裡面會記錄到目前為止我寫的文章 %}

<br><br>

另外提醒各位，我沒有關掉推薦文章，因此透過連結，可以找到下一關卡，但...你覺得我會那麼笨嗎？
!!! 最好不要跳關，照著關卡一步一步來，不然你到最後就知道了 !!! <br><br>

</font>
<font size="5">



*線索埋藏於網頁中，我只不過是提問罷了。*
*密碼是我提的問題，而答案... 你們要自己尋找。*<br><br>



</font>



# Game Start !!! (Beginning)

<font size="4">

這雖然是遊戲，但真的是鬧著玩的。<br>

既然這也是遊戲，首先致敬一下之前最常玩的遊戲，讓我認識了許多人，而且還有持續聯絡，該遊戲的倒閉時間為<strong>5/24(1D)</strong>，現在能玩遊戲都算一種奢侈了，這一關只是讓使用者大概了解是甚麼形式，之後的關卡會加入一些額外的元素。<br>

目前還沒去看怎麼在網頁上執行，所以自己去弄吧 (つ´ω`)つ <br>

你需要找到數字，並透過推測數字來反推出原本的密碼，只要輸入對，正確的密碼就會出來了，之後會以書的方式呈現提示。 (✪ω✪)<br>

提示: "NRRN" <br>

如果你會寫 code，那你可以去看一下或執行一下下面的code，如果你不會寫..，可能對你有點小難，但...就去嘗試看看吧。<br>

</font>

<br>

``` C
#include <stdio.h>

#define SIZE 4

int main(){
    char str[4]="NRRN";
    char input[4];
    int x;
    printf("Enter the correct number to gain the password (Ctrl + z or Ctrl + c to over):\n");
    while(scanf("%d", &x)!=EOF){
        for(int i=0;i<SIZE;i++){
            input[i] = str[i];
        }
        for(int i=0;i<SIZE;i++){
            input[i] -= x;
        }
        
        for(int i=0;i<SIZE;i++){
            printf("%c", input[i]);
        }
        printf("\n");
    }

    return 0;
}

```

<script type="text/javascript">
    function link_display(){
        document.getElementById('times').innerHTML="D.S."
        var data=document.getElementById("time"); //time
                
        if(data.style.display=="block"){
            data.style.display="none";
        }
        else{
            data.style.display="block";
        }
    }

    passwords="1551"
    function Level1(){
        location.href='https://seclusioner.github.io/2023/02/12/level1/'
    }
    function password() {
        if(prompt('請輸入密碼：', "password") == passwords){
            SAONotify('GO TO LEVEL1','恭喜即將踏上旅途', 'Level1();');
        }
        else{
            SAONotify('ERROR','密碼錯誤！');
        }
    }
</script>

<div style="background-image: linear-gradient(-20deg, #fc6076 0%, #ff9a44 100%); color: white;  font-size: 16px; margin-bottom: 5px; padding: 8px; text-align:center;">
    <b><div onclick ="link_display();"><i style="text-align:right;">2023.02 D.S.</i></div></b>
    <a href="javascript:password()"><b id="time"><span id="times" style="color:rgb(163, 163, 163)"></span></b></a>
</div>

<br>
