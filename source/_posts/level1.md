---
title: KEEP X SEARCHING
date: 2023-02-12 23:59:58
tags:
- [Level]
category: 
- [Level]
description: Level 1
cover: https://images8.alphacoders.com/105/1059623.jpg
top_img: https://images8.alphacoders.com/105/1059623.jpg
swiper_index: 3
---
<body onload="SAONotify('KEEP X SEARCHING','<i>從文字找出線索吧！</i><br><i>跟著我一起進入我的世界之中。</i>');"></body>

<!-- +1234 -->

<!-- more -->

<div class="box_hide">
<div class="content_hide">
    <p>574 (16-1)</p>
</div>
</div>

<style>
.box_hide {
    width: 745px;
    height: 25px;
    background-color: #ffffff;
    position: relative;
    justify-content: center;
    overflow: hidden;
}

.box_hide:hover .content_hide {
    opacity: 1;
    visibility: visible;
}

.content_hide {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(255, 255, 255, 0.9);
    opacity: 0;
    visibility: hidden;
    transition: opacity 0.3s ease-in-out;
}

.content_hide p {
    margin: 0.1px;
    font-size: 2px;
    text-align: center;
}
</style>


# 尋找吧 !

<font size="4">
人生是一種探索自我的過程，不斷學習，提升自己；不斷嘗試，累積經驗；不斷往前，永不停留。<br>

沒有一定的答案，沒有被決定的人生與命運，在不斷輪迴的現實之中，與自己戰鬥。<br>

在這無情的現實中，尋找不同的東西，去得到自己想要的東西，找到生命的意義。<br>

有些要自己追尋，有些要自己發掘；有些已然在眼前，有些卻遙不可及。<br>

希望你能一起，踏上旅途，擁有一段美好的旅程。 <br>
不要讓自己後悔，也不要猶豫不前，試著相信自己看看，你 ----- 只需要一點勇氣。<br>

尋找通往前方的<strong>鑰匙</strong>，打開心中的<strong id="click-me">門</strong>，朝著目的地，勇往直前，但要記得回頭看看過去的路程，不要一味地向著前方，也不要忘記，旅途中所看到的東西。<br>
</font>

<div id="password-form">
    <div class="close-button">&times;</div>
    <form>
        <label for="password">(+)既然找到了，輸入密碼吧(輸入錯誤會無法前往下一關)：</label>
        <input type="password" id="password" name="password" placeholder="請輸入密碼">
        <input type="submit" value="提交">
    </form>
</div>

<script type="text/javascript">
    password = "1234"
    const clickMe = document.getElementById('click-me');
    const passwordForm = document.getElementById('password-form');
    const passwordInput = document.getElementById('password');
    const closeButton = document.querySelector(".close-button");

    clickMe.addEventListener('click', () => {
        passwordForm.style.display = 'block';
        passwordInput.focus();
    });

    function Level2(){
        location.href='https://seclusioner.github.io/2023/02/12/level2/'
    }
    
    passwordForm.addEventListener('submit', (event) => {
        event.preventDefault();
        
        if(passwordInput.value==password){
            SAONotify('GO TO LEVEL2','恭喜你破了第一關，即將前往第二關', 'Level2();');
        }else{
            SAONotify('ERROR','密碼錯囉！');
        }
        // 隱藏表單並清除輸入欄
        passwordForm.style.display = 'none';
        passwordInput.value = '';
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
        background-color: #4CAF50;
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

    	/*--------------------*/
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
</style>

<br>

<div style="background-image: linear-gradient(-20deg, #fcf400 0%, #fa8f15 100%); color: white;  font-size: 16px; margin-bottom: 5px; padding: 8px; text-align:center;"><b>
<i style="text-align:right;">2023.02 D.S.</i></b>
</div>
