---
title: D.x S.
date: 2023-02-12 23:00:00
tags:
- [Level]
category: 
- [Level]
description: 最後一關！
cover: https://images.fineartamerica.com/images/artworkimages/mediumlarge/2/japanese-winter-armand-michel.jpg
top_img: https://images.fineartamerica.com/images/artworkimages/mediumlarge/2/japanese-winter-armand-michel.jpg
swiper_index: 9
---

<body onload="SAONotify(' D. x  S. ', '1. 可以去從文意分析、猜字<br>2. 注意文字')"></body>

<!-- more -->

<br>

<div id="moving-object" style="margin-bottom: 5px; padding: 4px; text-align:center;"><a href="http://seclusioner.github.io/DS.github.io">D.S.</a></div>

<script type="text/javascript">
    var object = document.getElementById("moving-object");
    var pageWidth = document.documentElement.clientWidth;
    var pageHeight = document.documentElement.clientHeight;

    object.addEventListener("mouseover", function() {
        var newLeft = Math.floor(Math.random() * (pageWidth - object.offsetWidth));
        var newTop = Math.floor(Math.random() * (pageHeight - object.offsetHeight));
        object.style.left = newLeft + "px";
        object.style.top = newTop + "px";
    });
    
</script>
<style type="text/css">
    #moving-object {
        width: 35px;
        height: 35px;
        background-color: #ff0000;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        opacity: 20%;
    }
</style>

<h1> 前言 </h1>

<font size="4">

人生只是永無止境的輪迴中的一場夢，而生命在每個階段都扮演著不同的角色，其中，有些人是「真正」的活著的，因為他們不拘束於生活、金錢、名聲等那些物質之事，因為他們找到了活著的某種「意義」，當尋找這如夢似幻的東西之時，或許會擁有與眾不同的人生，而追尋的東西因人而異 ...... <br>

人，只是滄海一粟罷了，人生所謂的意義為何？<br>
活著有甚麼責任或義務呢？<br>
一如既往的生活，一切的一切，始終是過眼雲煙，人們不斷為生活打拼，生活不斷歷練著人們，這是場永無止境的戰鬥。<br>
在輪迴之中，不論是哪一世，哪種身分，應該都是這樣的吧？ 生命，只不過是旅行中那短暫的一頁... <br><br>

沒有絕對的對與錯，只是每個人都有所追求。 <br>
那麼我追求的，是什麼呢？ <br>

</font>


<!-- 自介 -->
<h1 id="click-me">D.S.</h1>
<div id="password-form">
    <div class="close-button">&times;</div>
    <form>
        <label for="password">你認為D.S.代表甚麼呢？(兩個字)：</label>
        <input type="password" id="password" name="password">
        <input type="submit" value="OK">
    </form>
</div>
<div id="hint" style="display: none;">
    <div class="close-button2">&times;</div>
    <form>
        <mark><i>*鑰匙為所有密碼做運算的結果，運算符號每一關入口皆有標示*</i></mark>
    </form>
    <br>
</div>

<script type="text/javascript">
    password = "夢隱";
    const clickMe = document.getElementById('click-me');
    const passwordForm = document.getElementById('password-form');
    const passwordInput = document.getElementById('password');
    const closeButton = document.querySelector(".close-button");
    const closeButton2 = document.querySelector(".close-button2");
    const hint = document.getElementById('hint');
    clickMe.addEventListener('click', () => {
        passwordForm.style.display = 'block';
        passwordInput.focus();
    });
    passwordForm.addEventListener('submit', (event) => {
        event.preventDefault();
        if(passwordInput.value==password || passwordInput.value=="a/4up3"){ // 鑰匙為所有密碼做運算的結果，運算符號每一關入口皆有標示
            hint.style.display = 'block';
        }else{ // 再想想看吧！
            SAONotify('ERROR', '再想想看吧！')
        }
        passwordForm.style.display = 'none';
        passwordInput.value = '';
        closeButton2.addEventListener("click", function() {
            hint.style.display = "none";
        });
    });
    closeButton.addEventListener("click", function() {
        passwordForm.style.display = "none";
    });
</script>
<style type="text/css">
    body {
        background-color: #F5F5F5;
        font-family: Arial, sans-serif;
    }
    
    #password-form {
        display: none;
        position: fixed;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 300px;
        background-color: #FFFFFF;
        padding: 30px;
        border-radius: 5px;
        box-shadow: 0px 0px 5px #CCCCCC;
    }
    
    label {
        display: block;
        margin-bottom: 5px;
        color: #333333;
        font-size: 16px;
    }
    
    input[type="password"] {
        display: block;
        width: 100%;
        padding: 10px;
        border-radius: 5px;
        border: 1px solid #CCCCCC;
        font-size: 16px;
        box-sizing: border-box;
        margin-bottom: 10px;
    }
    
    input[type="submit"] {
        background-color: #dd1414;
        color: #FFFFFF;
        border: none;
        padding: 10px 20px;
        border-radius: 5px;
        font-size: 16px;
        cursor: pointer;
    }
    
    input[type="submit"]:hover {
        background-color: #3E8E41;
    }
    .close-button {
        position: absolute;
        top: 10px;
        right: 10px;
        width: 30px;
        height: 30px;
        background-color: #f0efef;
        border-radius: 50%;
        color: #282626;
        font-size: 20px;
        font-weight: bold;
        text-align: center;
        line-height: 30px;
        cursor: pointer;
    }
    .close-button2 {
        position: relative;
        top: -50px;
        right: -600px;
        width: 23px;
        height: 23px;
        background-color: #f0efef;
        border-radius: 50%;
        color: #282626;
        font-size: 20px;
        font-weight: bold;
        text-align: center;
        line-height: 20px;
        cursor: pointer;
    }
</style>

<!-- ------------------------------------------------------ -->

<font size="4">

<i><span id="myText1" onclick="toggleText1()">我喜歡天馬行空的想像</span>，<span id="myText2" onclick="toggleText2()">不喜歡展現真正的自己</span>。</i> <br>

*於心中的世界，盡情的綻放自我。* <br>

*這，才是真實的<strong>我</strong>。* <br>

</font>

<script  type="text/javascript">
    function toggleText1() {
        var element = document.getElementById("myText1");
        if (element.innerHTML == "我喜歡天馬行空的想像") {
            element.innerHTML = "d _ _ _ _";
        } else {
            element.innerHTML = "我喜歡天馬行空的想像";
        }
    }
    function toggleText2() {
        var element = document.getElementById("myText2");
        if (element.innerHTML == "不喜歡展現真正的自己") {
            element.innerHTML = "link";
        } else {
            element.innerHTML = "不喜歡展現真正的自己";
        }
    }
</script>


## 我


<font size="4">

固執是我的特質，堅持是我的態度，與眾不同是我的風格； <br>
貫徹信念，不論別人怎麼說我，反正又不會違反善良風俗； <br>
自身的缺陷或盲點，我會虛心接受你的建議。<br>

面對我想做好的事情，只要我有一口氣，我做到死也要把它做好，目標只有做到完美，做到自己滿意為止。<br>

時常追求跟別人不同的東西，常常與現實背道而馳，也因此時常懷疑自己，但不屈服於現實，是我的作風，不過要想成為理想的自己，我還得繼續努力。<br>

或許沒有極高的天賦，但有過人的毅力與耐力。 <br>
對於金錢名利沒有興趣，只希望自己能夠很有能力。 <br>

以學生的身分驗證，求學是最明顯的例子。 <br>

</font>


## 求學


<font size="4">

制度與觀念使得大部分學生都是以文憑、成績、學歷為讀書目的，但我從小到大，壓根沒想過要為了這些沒什麼太大意義的東西學習，學習是永無止境的，可能一個小地方就有很大的學問，只有拼命學習和累積經驗，才有可能往更高的境界邁進。 <br>

為了保持成績上好學校，很多學生選了很少的課程；為了考到好學校，有學生不斷補習刷題；為了能有好的成績、排名，有些學生不擇手段；但這些，在充滿數字的一張紙上，你看不出來。<br>

你看不出學生真正的學習過程；你看不出教授給分數的基準；你看不出他的人格特質與心理素質，因為那些數字跟學歷一旦沒達到你的標準，沒達到制度的"要求"，你根本不會看他的其他事項。 <br>

現實是結果，而不是過程。 <br>

但過程，卻往往才是最重要的。 <br>

我會不斷的以我的方式去學習任何東西，累積經驗。 <br>
我的目標從來就不是學歷，也不是成績排名，那些分數與文字對我而言毫無意義。 <br>
而一直支撐著我的最大動力來源，就是**興趣**。<br>

</font>


## 興趣


<font size="4">

興趣是很可怕的力量，它會讓你不斷有動力去提升自己，讓自己變得更好、更完美，因為你總是想把它做好。<br>

小時候是圍棋、美術、籃球，自從發現專業性的興趣，對所有有關"電"或是說"科技"的事物都有興趣，不論是硬體、軟體，類比、數位，理論實作，我都會竭盡所能去學得更好，這條路很長且沒有盡頭，只能不斷讓自己變得更好，精益求精，並達到對自己的**期許**。<br>

</font>

# 期許

## 學習


<font size="4">

就是各個科目學精、學扎實，並應用在實作上。<br>
實作時腦袋可以連結各個科目，把無數的數學公式、專業理論連結起來，並用出來，知道實作為甚麼要這樣做、應該怎麼做、下一步是什麼，而我對學習的期許之一，就是改變台灣的教育制度和體系，即使不一定可以做到，我也要以我的方式證明我自己不是錯的，證明自己有**能力**。 <br>

</font>


## 能力


<font size="4">

不用談天賦，既然是已成定局的事情，就不用那麼多廢話，做就對了，不論理論實作、生活，讓自己能力不斷提升，突破自己的極限。 <br>

希望能讓看到這裡的你，更知道我的想法。<br>

也謝謝你願意看到這裡，Good Luck!。  [終わり](https://seclusioner.github.io/2023/02/12/End/) <br><br>

</font>

<!----------------------------------------------------->
<div style="background-image: linear-gradient(-20deg, #1123c7 0%, #00fc3f 100%); color: white;  font-size: 16px; margin-bottom: 5px; padding: 8px; text-align:center;"><b>
<i style="text-align:right;">2023.02 D.S.</i></b>
</div>

