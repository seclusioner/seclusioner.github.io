---
title: Begin X End
date: 2023-02-12 00:00:01
tags:
- [Level]
category: 
- [Level]
description: 是結束，抑或是開始？
cover: https://i.pinimg.com/564x/4c/9a/f7/4c9af7d2db35d3090eb4c78d908c8c9b.jpg
top_img: https://i.pinimg.com/564x/4c/9a/f7/4c9af7d2db35d3090eb4c78d908c8c9b.jpg
swiper_index: 10
---

<body onload="SAONotify('BEGIN X END ?','<i>這裡是關卡破完後最後進入的入口，如果你前面還沒破完，建議不要點開。</i>')"></body>

<script async src="https://npm.elemecdn.com/tzy-blog/lib/js/other/sakura.js"></script>

<!-- more -->

<font size="4">


是結束，也是開始。 <br>
願你我都可以找到人生的<b>意義</b>。 <br>

<p>去尋找吧!</p>


</font>

<input type="password" id="meaning">
<div class="door hidden" id="door"></div>
<div class="door-knob hidden" id="door-knob"></div>

<br><br>

<script type="text/javascript">
    const passwordInput = document.getElementById('meaning');
    const door = document.getElementById('door');
    const doorKnob = document.getElementById('door-knob');
    const sum = '11924'; //1551 + 1234 - 15 + 8859 - 260 - 1460 + 2015
    passwordInput.addEventListener('input', () => {
        if (passwordInput.value === sum) {
          SAONotify('ENTRANCE OPEND', '入口已開啟，感謝您的遊玩！！！')
            passwordInput.classList.add('hidden');
            door.classList.remove('hidden');
            doorKnob.classList.remove('hidden');
        }
    });
    doorKnob.addEventListener('mouseover', () => {
        door.style.transform = 'rotateY(-90deg)';
    });
    door.addEventListener('transitionend', () => {
        window.location.href = 'https://seclusioner.github.io/DS.github.io'; // 替換為您想要前往的網頁的URL
    });
</script>
<style type="text/css">
* {
			margin: 0;
			padding: 0;
			box-sizing: border-box;
		}

		.door {
			position: relative;
			width: 100%;
			height: 600px;
			background-color: #f0f0f0;
			border: 5px solid #444;
			border-radius: 10px;
			box-shadow: 0 0 10px rgba(0, 0, 0, 0.4);
			transform-origin: left center;
			transition: transform 0.5s ease-in-out;
		}

		.door:before {
			content: "";
			position: absolute;
			top: 0;
			left: 50%;
			transform: translateX(-50%);
			width: 8px;
			height: 595px;
			background-color: #666;
			border-radius: 4px;
		}

		.door:after {
			content: "";
			position: absolute;
			top: 590px;
			left: 0;
			width: 790px;
			height: 8px;
			background-color: #666;
			border-radius: 4px;
		}

		.door-knob {
			position: absolute;
			top: 500px;
			left: 60px;
			width: 30px;
			height: 30px;
			background-color: #666;
			border-radius: 50%;
			cursor: pointer;
		}

		.hidden {
			display: none;
		}
</style>

