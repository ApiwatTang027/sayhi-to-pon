<!DOCTYPE html>

<html lang="th">

<head>

  <meta charset="UTF-8">

  <title>จดหมายจากคนแปลกที่รู้จัก</title>

  <style>

    body {

      margin: 0;

      padding: 0;

      background-color: #000;

      color: white;

      font-family: 'Kanit', sans-serif;

      overflow-x: hidden;

      min-height: 100vh;

      display: flex;

      flex-direction: column;

      align-items: center;

    }



    h1 {

      font-size: 4em;

      margin: 50px 0 20px 0;

      text-align: center;

    }



    .box {

      text-align: center;

      background-color: rgba(255, 255, 255, 0.05);

      border: 2px solid white;

      border-radius: 12px;

      padding: 30px 40px;

      box-shadow: 0 0 20px white;

      animation: pulse 3s infinite;

      max-width: 700px;

      margin-bottom: 80px;

    }



    @keyframes pulse {

      0%, 100% { box-shadow: 0 0 10px white; }

      50% { box-shadow: 0 0 30px white; }

    }



    button {

      margin-top: 20px;

      padding: 10px 20px;

      font-size: 1em;

      background: transparent;

      color: white;

      border: 1px solid white;

      border-radius: 5px;

      cursor: pointer;

    }



    button:hover {

      background-color: white;

      color: black;

    }



    #secret {

      margin-top: 25px;

      font-size: 1.3em;

      color: #ccc;

      display: none;

    }



    .friend-img {

      margin-top: 20px;

      width: 250px;

      border-radius: 12px;

      box-shadow: 0 0 10px white;

    }



    .snowflake {

      position: fixed;

      top: -10px;

      background: white;

      border-radius: 50%;

      opacity: 0.7;

      pointer-events: none;

      animation: fall linear infinite;

      z-index: 0;

    }



    @keyframes fall {

      to {

        transform: translateY(100vh);

        opacity: 0;

      }

    }



    #feeling-box {

      display: none;

      margin-top: 30px;

    }



    #feeling-box div {

      background-color: rgba(255, 255, 255, 0.08);

      border: 1px solid white;

      padding: 20px;

      border-radius: 10px;

      max-width: 500px;

      margin: 0 auto;

      color: #eee;

      box-shadow: 0 0 10px white;

      font-size: 1.1em;

    }



    #reply-box {

      margin-top: 40px;

    }



    textarea {

      width: 100%;

      max-width: 500px;

      padding: 10px;

      font-size: 1em;

      border-radius: 10px;

      border: 1px solid white;

      background-color: rgba(255, 255, 255, 0.1);

      color: white;

      resize: none;

      margin-top: 10px;

    }



    #reply-display {

      margin-top: 20px;

      display: none;

      border: 1px solid white;

      border-radius: 10px;

      padding: 15px;

      max-width: 500px;

      background-color: rgba(255, 255, 255, 0.08);

      color: #eee;

      box-shadow: 0 0 10px white;

    }



    @keyframes fadeIn {

      0% { opacity: 0; transform: translateY(10px); }

      100% { opacity: 1; transform: translateY(0); }

    }



    .fade-in {

      animation: fadeIn 1.5s ease-out forwards;

    }

  </style>

</head>

<body>



  <h1>จดหมายแทนความรู้สึก ❄️</h1>



  <div class="box">

      <p>ถึงเพื่อนๆที่ดีและกวนตีนคำพูดกูอาจไม่หวานมีแต่ความจริงใจให้ตลอด</p>

    <p>ขอบคุณที่อยู่ด้วยกันในทุกช่วงเวลาขอบคุณที่โลกเวี่ยงพวกมึงมานะ</p>

    <p>แยกย้ายกันไปทำงานแล้วนัดกันมาเที่ยวมั่งนะอยากเม้าท์5555อย่าน้อยใจนะรูปดีๆมีแค่นี้ที่เหลือรูปหลุด555555💫</p> 💫</p>



    <!-- ปุ่มเปิดข้อความลับ -->

    <button onclick="reveal()">เปิดข้อความลับ 🤍</button>



    <!-- ข้อความลับ -->

    <p id="secret">ขอให้พวกมึงโชคดีในทุกๆการเติบโต 💌</p>



    <!-- กล่องความรู้สึก -->

    <div id="feeling-box">

      <div>

        บางทีกูอาจไม่ได้พูดบ่อยนัก<br>

        แต่เรารู้สึกโชคดีมากที่ได้รู้จักพวกมึงจริงๆ<br><br>

        เวลาผ่านไปไวเหมือนโกหกมีทั้งความทรงจำที่มีกันเสมอทั้ง สนุก ทุกข์ เศร้าป่นกันไปทะเลาะกันมั่ง<br>

        และหวังว่าจะได้อยู่กันครบกลุ่มด้วยกันอีกนะ 🖤

      </div>

    </div>



    <!-- กล่องให้เพื่อนตอบกลับ -->

    <div id="reply-box">

      <p style="color: #aaa;">อยากบอกอะไรกลับมาไหม? 😊</p>

      <textarea id="reply-input" placeholder="พิมพ์ข้อความตรงนี้..." rows="4"></textarea>

      <br>

      <button onclick="showReply()">ส่งคำตอบ 💬</button>



      <div id="reply-display"></div>

    </div>

  </div>



  <!-- หิมะตก -->

  <script>

    function reveal() {

      const secret = document.getElementById("secret");

      const feelingBox = document.getElementById("feeling-box");



      secret.style.display = "block";

      feelingBox.style.display = "block";



      secret.classList.add("fade-in");

      feelingBox.classList.add("fade-in");

    }



    function showReply() {

      const input = document.getElementById("reply-input").value.trim();

      const display = document.getElementById("reply-display");



      if (input) {

        display.innerHTML = "เพื่อนตอบกลับว่า:<br><br><em>“" + input + "”</em>";

        display.style.display = "block";

        display.classList.add("fade-in");

      }

    }



    function createSnowflake() {

      const snowflake = document.createElement("div");

      snowflake.classList.add("snowflake");

      snowflake.style.width = snowflake.style.height = Math.random() * 5 + 2 + "px";

      snowflake.style.left = Math.random() * 100 + "vw";

      snowflake.style.animationDuration = Math.random() * 5 + 5 + "s";

      document.body.appendChild(snowflake);

      setTimeout(() => snowflake.remove(), 10000);

    }



    setInterval(createSnowflake, 100);

  </script>



</body>

</html>
