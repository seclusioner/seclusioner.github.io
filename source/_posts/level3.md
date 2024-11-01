---
title: 愛 X 情
date: 2023-02-12 23:59:56
tags:
- [Level]
category: 
- [Level]
description: Level 3
cover: https://i.pinimg.com/564x/43/7e/a7/437ea77a3e41f2ee466ef4fbeaf6b3a6.jpg
top_img: https://i.pinimg.com/564x/43/7e/a7/437ea77a3e41f2ee466ef4fbeaf6b3a6.jpg
swiper_index: 5
---

<body onload="SAONotify('愛 X 情','<i>這關不難想，加油吧</i>');"></body>

<!-- +8859 -->

# 致 - 重要的人

<font size="4">
時間悄悄的流逝，偷走了人們的歲月，並一步一步地帶向是起點亦是終點的道路，對某些人而言，你是不可或缺的存在，對某些人而言，你是他們值得信賴、依靠的人，對某些人而言，你是他們願意犧牲自己的人生的人 …，而於你的人生中，總是有「某些人」為你付出、為你擔憂，當然也有「某些人」因你嫉恨、因你產生仇恨，不論誰認為的如何，在你的人生中擔任什麼樣的角色，你對於某個人，就是一個獨一無二的存在。<br>
<br>
可以為一個人犧牲奉獻、無私的付出，是極為不易的，我第一個想到的，便是<span id="dad" onclick="toggleText_DAD()">父</span><span id="mom" onclick="toggleText_MOM()">母</span>。離家後，相見從一件平凡而幸福的事情變為一種極為奢侈的奢求與期望，經常會感嘆自己的幸運，也會因自己的自私與無能而感到自責與憤怒，歲月帶走了健康，改變了面容，但那份「<span id="click-me">愛/情</span>」，是永恆不變的，不論任何千言萬語，都無法一語道盡，至少，請讓我用最真誠的心，與感激的態度，對你們說聲謝謝，對不起，辛苦你們了。
</font>
<br/>

<div id="password-form">
<div class="close-button2">&times;</div>
<form>
    <label for="password">(+)輸入你所推測的數字吧！：</label>
    <input type="password" id="password" name="password" placeholder="請輸入密碼">
    <input type="submit" value="GO!">
    <br>
</form>
</div>

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
        background-color: #ff8c00;
        color: #000000;
        border: none;
        padding: 10px 20px;
        border-radius: 5px;
        font-size: 16px;
        cursor: pointer;
    }
    
    input[type="submit"]:hover {
        background-color: #3E8E41;
    }
/*--------------------*/
.close-button2 {
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
</style>
<script type="text/javascript">
    function toggleText_DAD() {
        var element = document.getElementById("dad");
        if (element.innerHTML == "父") {
            element.innerHTML = "8/8";
        } else {
            element.innerHTML = "父";
        }
    }
    function toggleText_MOM() {
        var element = document.getElementById("mom");
        if (element.innerHTML == "母") {
            element.innerHTML = "日 <-> 5/2"; // 5/2 + 7 = 5/9
        } else {
            element.innerHTML = "母";
        }
    }

    password = "8859"
    const clickMe = document.getElementById('click-me');
    const passwordForm = document.getElementById('password-form');
    const passwordInput = document.getElementById('password');
    const closeButton2 = document.querySelector(".close-button2");

    clickMe.addEventListener('click', () => {
        passwordForm.style.display = 'block';
        passwordInput.focus();
    });
    
    function level4(){
        location.href='https://seclusioner.github.io/2023/02/12/level4/'
    }

    passwordForm.addEventListener('submit', (event) => {
        event.preventDefault();
        
        if(passwordInput.value==password){
            SAONotify('GO TO LEVEL4','往第四關邁進吧～', 'level4();');
        }else{
            SAONotify('ERROR','不難想，再試試看吧！');
        }
        // 隱藏表單並清除輸入欄
        passwordForm.style.display = 'none';
        passwordInput.value = '';
    });

    closeButton2.addEventListener("click", function() {
        passwordForm.style.display = "none";
    });

</script>

<br>
<div style="background-image: linear-gradient(-20deg,  #1d1964 0%, #00fcef 100%); color: white;  font-size: 16px; margin-bottom: 5px; padding: 8px; text-align:center;"><b>
    <i style="text-align:right;">2023.02 D.S.</i></b>
</div>
<br/>
<br/>
