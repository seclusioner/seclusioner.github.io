---
title: Message X Decoding
date: 2023-02-12 23:59:54
tags:
- [Level]
category: 
- [Level]
description: Level 5
cover: https://i.pinimg.com/564x/3d/a7/b0/3da7b08ca4424e50a1ddfaa7e87c303b.jpg
top_img: https://i.pinimg.com/564x/3d/a7/b0/3da7b08ca4424e50a1ddfaa7e87c303b.jpg
swiper_index: 7
---

<body onload="SAONotify('Message X Decoding','<i>I N V E R S E x E N C O D E</i>');"></body>

<font size="4">
我留下了一個訊息，把它解出來吧！<br><br>
</font>

<!-- Hint:   x=Ab，b=? -->

<!-- -------------- | 2 | 4 | 9 | -------------- | 3 | 5 | 1 |-------------- | 7 | 8 | 6 |-------------- -->

<div class="nine">
<div class="container_nine">
    <div class="cell" data-text="(1,0)">3</div>
    <div class="cell" data-text="(0,1)">4</div>
    <div class="cell" data-text="(2,2)">6</div>
    <div class="cell" data-text="(0,0)">2</div>
    <div class="cell" data-text="(1,2)">1</div>
    <div class="cell" data-text="(1,1)">5</div>
    <div class="cell" data-text="(2,1)">8</div>
    <div class="cell" data-text="(2,0)">7</div>
    <div class="cell" data-text="(0,2)">9</div>
</div>
</div>

<script type="text/javascript">
    let cells = document.querySelectorAll('.cell');
    cells.forEach(cell => {
    let originalText = cell.innerText;
    let newText = cell.dataset.text;
    cell.addEventListener('click', () => {
        if (cell.classList.contains('active')) {
        cell.classList.remove('active');
        cell.innerText = originalText;
        } else {
        cell.classList.add('active');
        cell.innerText = newText;
        }
    });
    });  
</script>
<style type="text/css">
    .nine{
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 2;
        background-color: #f2f2f2;
    }
    
    .container_nine {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(3, 1fr);
        gap: 20px;
        background-color: #fff;
        border: 2px solid #333;
        border-radius: 10px;
        padding: 20px;
        box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.2);
    }
    
    .cell {
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 24px;
        font-weight: bold;
        color: #333;
        background-color: #ddd;
        border: 2px solid #333;
        border-radius: 5px;
        cursor: pointer;
        transition: all 0.2s ease-in-out;
        width: 100px;
        height: 100px;
        user-select: none;
    }
    
    .cell:hover {
        background-color: #333;
        color: #fff;
    }
    
    .cell.active {
        background-color: #333;
        color: #fff;
    }
</style>

<br><br>

<table>
    <tr>
    <td>0</td>
    <td>1</td>
    <td>2</td>
    <td>3</td>
    <td>4</td>
    <td>5</td>
    <td>6</td>
    <td>7</td>
    <td>8</td>
    <td>9</td>
    <td>10</td>
    <td>11</td>
    <td>12</td>
    <td>13</td>
    <td>14</td>
    <td>15</td>
    <td>16</td>
    <td>17</td>
    <td>18</td>
    <td>19</td>
    <td>20</td>
    <td>21</td>
    <td>22</td>
    <td>23</td>
    <td>24</td>
    <td>25</td>
    <td>26</td>
    </tr>
    <tr>
    <td>A</td>
    <td>B</td>
    <td>C</td>
    <td>D</td>
    <td>E</td>
    <td>F</td>
    <td>G</td>
    <td>H</td>
    <td>I</td>
    <td>J</td>
    <td>K</td>
    <td>L</td>
    <td>M</td>
    <td>N</td>
    <td>O</td>
    <td>P</td>
    <td>Q</td>
    <td>R</td>
    <td>S</td>
    <td>T</td>
    <td>U</td>
    <td>V</td>
    <td>W</td>
    <td>X</td>
    <td>Y</td>
    <td>Z</td>
    <td> </td>
    </tr>
</table>

<br><br>

<font size="4">
加密後的訊息：

&emsp; &emsp; 
*192   &emsp;250   &emsp;179 &emsp; 280   &emsp;390   &emsp;323 &emsp; 127   &emsp;152   &emsp;138 <br><br>*


$$
\begin{bmatrix}
  &?  &? &? & \\
  &?  &? &? & \\
  &?  &? &? & \\
\end{bmatrix}
$$

</font>

<br>


<font size="4">
透過上面的線索，輸入我留下的訊息吧：<br>
</font>

<input id="password" type="text"><br>
<button id="submit">提交</button>
<p id="hint"></p>

<script type="text/javascript">
    var password = "FOUR YEAR"; 
    var submitBtn = document.getElementById("submit");
    var hintDiv = document.getElementById("hint");
    
    function Level6(){
        location.href='https://seclusioner.github.io/2023/02/12/level6/'
    }

    submitBtn.onclick = function() {
    var guess = document.getElementById("password").value;
    if (guess === password) {
        hintDiv.style.color = "green";
        hintDiv.innerHTML += "(-)恭喜你解出訊息，記住這關的數字(文字即是這一關的鑰匙(密碼))，另外YEAR不加S是因為編碼過程，S剛剛好多出來 -W-"; //1460
        document.getElementById("password").disabled = true;
        document.getElementById("submit").disabled = true;
        SAONotify('GO TO LEVEL6', '往第六關邁進', 'Level6();');
    }else{
        SAONotify('ERROR','解碼失敗！');
    }
    };
</script>

<style type="text/css">
    #password {
    margin-top: 50px;
    font-size: 36px;
    letter-spacing: 10px;
    text-align: center;
    background-color: #f7f7f7;
    border: none;
    outline: none;
    padding: 20px;
    width: 300px;
    height: 60px;
    box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
    }
    #submit {
    margin-top: 30px;
    font-size: 24px;
    background-color: #4CAF50;
    color: #fff;
    border: none;
    outline: none;
    padding: 10px 20px;
    border-radius: 4px;
    cursor: pointer;
    }
    #hint {
    margin-top: 30px;
    font-size: 24px;
    }
</style>