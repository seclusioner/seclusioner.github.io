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

<!-- 密碼輸入區（保持原本樣式） -->
<input type="password" id="passwordInput" placeholder="Enter password">
<p id="loginMessage" style="color:#f00; font-size:14px; margin-top:4px;"></p>
<button id="loginBtn">ENTER</button>

<!-- 終端機面板 -->
<section id="main_shell" style="display:none; margin-top:20px;">
  <h1 id="main_shell_greeting">Welcome, <em>root</em></h1>
  <h3 class="title"><p>Initializing system...</p></h3>
  <div id="main_shell_innercontainer">
    <pre id="terminal1" style="background:#000;color:#0f0;padding:10px;height:300px;overflow:hidden;font-family:monospace;"></pre>
  </div>
</section>

<!-- 閃白效果 -->
<div id="flash" style="position:fixed; top:0; left:0; width:100%; height:100%; background:#fff; opacity:0; pointer-events:none; transition: opacity 0.3s;"></div>

<script type="text/javascript">
/* ----------------- 密碼驗證 ----------------- */
const correctPassword = '11924'; //1551 + 1234 - 15 + 8859 - 260 - 1460 + 2015
const passwordInput = document.getElementById("passwordInput");
const loginBtn = document.getElementById("loginBtn");
const loginMessage = document.getElementById("loginMessage");

loginBtn.addEventListener("click", ()=>{
  const pw = passwordInput.value;
  if(pw === correctPassword){
    passwordInput.classList.add("hidden");
    loginBtn.classList.add("hidden");
    loginMessage.textContent = "";
    runTerminalAnimation(); // 正確密碼後呼叫動畫
  } else {
    loginMessage.textContent = "WRONG PASSWORD";
    passwordInput.value="";
    passwordInput.focus();
  }
});

passwordInput.addEventListener("keydown", (e)=>{
  if(e.key==="Enter") loginBtn.click();
});

/* ----------------- 終端機動畫 ----------------- */
function runTerminalAnimation() {
  /* ==============================
     建立 Overlay（不影響 body）
  ============================== */

  const overlay = document.createElement("div");
  overlay.id = "edexOverlay";

  Object.assign(overlay.style,{
    position:"fixed",
    top:0,
    left:0,
    width:"100%",
    height:"100%",
    background:"#050505",
    color:"#0f0",
    fontFamily:"monospace",
    overflow:"hidden",
    zIndex:9999,
    display:"flex",
    flexDirection:"row"
  });

  document.body.appendChild(overlay);


  /* ==============================
     三欄結構
  ============================== */

  const leftPanel=document.createElement("div");
  const mainShell=document.createElement("section");
  const rightPanel=document.createElement("div");

  Object.assign(leftPanel.style,{
    width:"240px",
    padding:"15px",
    borderRight:"1px solid #003344",
    overflowY:"auto",
    fontSize:"13px"
  });

  Object.assign(rightPanel.style,{
    width:"240px",
    padding:"15px",
    borderLeft:"1px solid #003344",
    overflowY:"auto",
    fontSize:"13px"
  });

  Object.assign(mainShell.style,{
    flex:"1",
    display:"flex",
    flexDirection:"column",
    padding:"20px",
    overflow:"hidden"
  });

  overlay.append(leftPanel,mainShell,rightPanel);


  /* ==============================
     中央終端
  ============================== */

  const title=document.createElement("h1");
  title.textContent="Welcome, root";
  title.style.margin="0";
  title.style.fontSize="22px";
  title.style.color="#00ffcc";

  const subtitle=document.createElement("div");
  subtitle.textContent="Initializing secure shell...";
  subtitle.style.marginBottom="15px";
  subtitle.style.color="#888";

  mainShell.append(title,subtitle);

  const terminal=document.createElement("pre");
  Object.assign(terminal.style,{
    flex:"1",
    background:"#000",
    padding:"15px",
    overflowY:"auto",
    border:"1px solid #003344",
    fontSize:"14px"
  });

  mainShell.appendChild(terminal);


  /* ==============================
     區塊工具
  ============================== */

  function createSection(titleText){
    const section=document.createElement("div");
    section.style.marginBottom="25px";

    const title=document.createElement("div");
    title.textContent=titleText;
    title.style.color="#00ccff";
    title.style.marginBottom="6px";
    title.style.borderBottom="1px solid #002222";
    title.style.paddingBottom="4px";
    title.style.fontWeight="bold";

    section.appendChild(title);
    return section;
  }


  /* ==============================
     左側內容
  ============================== */

  const sysSection=createSection("SYSTEM STATUS");

  const cpuP=document.createElement("p");
  const ramP=document.createElement("p");
  const netP=document.createElement("p");
  const secP=document.createElement("p");

  sysSection.append(cpuP,ramP,netP,secP);
  leftPanel.appendChild(sysSection);

  const leftChartSection=createSection("NETWORK FLOW");
  const leftChart=document.createElement("canvas");
  leftChart.width=220;
  leftChart.height=80;
  leftChartSection.appendChild(leftChart);
  leftPanel.appendChild(leftChartSection);

  const userSection=createSection("USER INFO");
  userSection.innerHTML+=`
    <p>USER: root</p>
    <p>ACCESS: ADMIN</p>
    <p>LOCATION: UNKNOWN</p>
    <p>STATUS: CONNECTED</p>
  `;
  leftPanel.appendChild(userSection);


  /* ==============================
     右側內容
  ============================== */

  const trafficSection=createSection("TRAFFIC MONITOR");
  const rightChart=document.createElement("canvas");
  rightChart.width=220;
  rightChart.height=100;
  trafficSection.appendChild(rightChart);
  rightPanel.appendChild(trafficSection);

  const radarSection=createSection("RADAR SCAN");
  const radarCanvas=document.createElement("canvas");
  radarCanvas.width=220;
  radarCanvas.height=180;
  radarSection.appendChild(radarCanvas);

  const radarText=document.createElement("p");
  radarText.textContent="Scanning for active nodes...";
  radarText.style.color="#888";
  radarSection.appendChild(radarText);

  rightPanel.appendChild(radarSection);

  const powerSection=createSection("POWER CORE");
  const gaugeCanvas=document.createElement("canvas");
  gaugeCanvas.width=200;
  gaugeCanvas.height=120;
  powerSection.appendChild(gaugeCanvas);

  const powerText=document.createElement("p");
  powerText.textContent="Stability: nominal";
  powerText.style.color="#ffaa00";
  powerSection.appendChild(powerText);

  rightPanel.appendChild(powerSection);


  /* ==============================
     假數據更新
  ============================== */

  function randomData(){
    cpuP.textContent="CPU: "+Math.floor(Math.random()*100)+"%";
    ramP.textContent="RAM: "+Math.floor(Math.random()*100)+"%";
    netP.textContent="NET: "+Math.floor(Math.random()*500)+" kb/s";
    secP.textContent="SECURITY: ENABLED";
  }

  setInterval(randomData,1000);
  randomData();


  /* ==============================
     曲線圖生成器
  ============================== */

  function createChart(canvas,color){
    const ctx=canvas.getContext("2d");
    let data=new Array(40).fill(50);

    function draw(){
      ctx.clearRect(0,0,canvas.width,canvas.height);
      ctx.beginPath();
      for(let i=0;i<data.length;i++){
        let x=(canvas.width/data.length)*i;
        let y=canvas.height-(data[i]/100)*canvas.height;
        i===0?ctx.moveTo(x,y):ctx.lineTo(x,y);
      }
      ctx.strokeStyle=color;
      ctx.lineWidth=2;
      ctx.stroke();
    }

    setInterval(()=>{
      data.push(Math.random()*100);
      data.shift();
      draw();
    },200);

    draw();
  }

  createChart(leftChart,"#00ff99");
  createChart(rightChart,"#00ccff");


  /* ==============================
     雷達動畫
  ============================== */

  const radarCtx=radarCanvas.getContext("2d");
  let angle=0;
  let radarPoints=[];
  for(let i=0;i<8;i++){
    radarPoints.push({x:Math.random()*220,y:Math.random()*180});
  }

  function drawRadar(){
    radarCtx.clearRect(0,0,220,180);

    radarCtx.strokeStyle="rgba(0,255,255,0.2)";
    for(let r=20;r<=90;r+=20){
      radarCtx.beginPath();
      radarCtx.arc(110,90,r,0,Math.PI*2);
      radarCtx.stroke();
    }

    radarCtx.beginPath();
    radarCtx.moveTo(110,90);
    radarCtx.lineTo(110+90*Math.cos(angle),90+90*Math.sin(angle));
    radarCtx.strokeStyle="#00ccff";
    radarCtx.lineWidth=2;
    radarCtx.stroke();

    radarPoints.forEach(p=>{
      radarCtx.fillStyle="#ff3355";
      radarCtx.beginPath();
      radarCtx.arc(p.x,p.y,3,0,Math.PI*2);
      radarCtx.fill();
    });

    angle+=0.03;
    requestAnimationFrame(drawRadar);
  }

  drawRadar();


  /* ==============================
     電力儀表
  ============================== */

  const gaugeCtx=gaugeCanvas.getContext("2d");
  let gaugeValue=50;

  function drawGauge(){
    gaugeCtx.clearRect(0,0,200,120);

    let cx=100,cy=100,r=80;

    gaugeCtx.beginPath();
    gaugeCtx.arc(cx,cy,r,Math.PI,0);
    gaugeCtx.strokeStyle="#222";
    gaugeCtx.lineWidth=10;
    gaugeCtx.stroke();

    let end=Math.PI+(gaugeValue/100)*Math.PI;

    gaugeCtx.beginPath();
    gaugeCtx.arc(cx,cy,r,Math.PI,end);
    gaugeCtx.strokeStyle="#ffaa00";
    gaugeCtx.lineWidth=10;
    gaugeCtx.stroke();

    gaugeCtx.fillStyle="#ffaa00";
    gaugeCtx.font="18px monospace";
    gaugeCtx.fillText(Math.floor(gaugeValue)+"%",75,90);
  }

  setInterval(()=>{
    gaugeValue=Math.random()*100;
    drawGauge();
  },1000);

  drawGauge();


  /* ==============================
     終端動畫 + 進度條
  ============================== */

  const scriptLines=[
    "boot --init system_core",
    "loading kernel modules...",
    "establishing secure connection...",
    "decrypting credentials...",
    "verifying identity...",
    "checking security clearance..."
  ];

  const lineAudio=new Audio("/assets/line.wav");
  lineAudio.volume=0.4;

  function typeLine(text,speed=35){
    return new Promise(resolve=>{
      const line=document.createElement("div");
      terminal.appendChild(line);

      let i=0;
      const interval=setInterval(()=>{
        line.textContent+=text[i];
        i++;
        terminal.scrollTop=terminal.scrollHeight;

        if(i===1){
          lineAudio.currentTime=0;
          lineAudio.play().catch(()=>{});
        }

        if(i>=text.length){
          clearInterval(interval);
          resolve();
        }
      },speed);
    });
  }

  function fakeProgressBar(){
    return new Promise(resolve=>{
      const container=document.createElement("div");
      container.style.background="#002222";
      container.style.height="10px";
      container.style.width="100%";
      container.style.margin="6px 0";

      const bar=document.createElement("div");
      bar.style.height="100%";
      bar.style.width="0%";
      bar.style.background="#ddff00ff";
      bar.style.transition="width 0.2s";

      container.appendChild(bar);
      terminal.appendChild(container);

      let progress=0;
      const interval=setInterval(()=>{
        progress += Math.random()*10+5;
        bar.style.width = Math.min(progress,100) + "%";
        terminal.scrollTop = terminal.scrollHeight;
        if(progress>=100){
          clearInterval(interval);
          resolve();
        }
      },150);
    });
  }

  async function runSequence(){
    for(let line of scriptLines){
      await typeLine("> "+line);
      await new Promise(r=>setTimeout(r,80));
    }

    await typeLine("> access --grant root");
    await fakeProgressBar();
    await typeLine("ACCESS GRANTED");
    await typeLine("Redirecting...");
    flashAndRedirect();
  }

  function flashAndRedirect(url="https://seclusioner.github.io/DS.github.io"){
    overlay.style.transition="opacity 0.6s";
    overlay.style.opacity="0";
    setTimeout(()=>{ window.location.href=url; },600);
  }

  runSequence();
}


</script>
