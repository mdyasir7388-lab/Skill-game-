<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Skill Game</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #111;
      color: white;
      text-align: center;
    }

    .box {
      max-width: 420px;
      margin: 60px auto;
      padding: 25px;
    }

    h1 {
      font-size: 38px;
      margin-bottom: 8px;
    }

    p {
      color: #aaa;
    }

    button {
      width: 100%;
      padding: 16px;
      margin-top: 15px;
      border: 0;
      border-radius: 10px;
      font-size: 18px;
      font-weight: bold;
    }

    #create {
      background: #00c853;
      color: white;
    }

    #join {
      background: #2979ff;
      color: white;
    }

    input {
      width: 100%;
      padding: 15px;
      margin-top: 20px;
      border-radius: 10px;
      border: 1px solid #555;
      background: #222;
      color: white;
      font-size: 17px;
      text-align: center;
    }

    #result {
      margin-top: 25px;
      padding: 15px;
      background: #222;
      border-radius: 10px;
      display: none;
    }

    #roomLink {
      word-break: break-all;
      color: #00e676;
    }
  </style>
</head>

<body>

  <div class="box">

    <h1>🎮 Skill Game</h1>
    <p>Play. Compete. Win.</p>

    <button id="create">CREATE ROOM</button>

    <input id="roomCode" placeholder="Enter Room Code">

    <button id="join">JOIN ROOM</button>

    <div id="result">
      <div>Your Room Code</div>
      <h2 id="showCode"></h2>
      <div id="roomLink"></div>
    </div>

  </div>

  <script>

    function createRoomCode() {
      const chars = "ABCDEFGHJKLMNPQRSTUVWXYZ23456789";
      let code = "";

      for (let i = 0; i < 5; i++) {
        code += chars[Math.floor(Math.random() * chars.length)];
      }

      return code;
    }

    document.getElementById("create").onclick = function () {

      const code = createRoomCode();

      document.getElementById("showCode").textContent = code;

      const link =
        window.location.origin +
        window.location.pathname +
        "?room=" +
        code;

      document.getElementById("roomLink").textContent = link;

      document.getElementById("result").style.display = "block";
    };


    document.getElementById("join").onclick = function () {

      const code =
        document.getElementById("roomCode").value
        .trim()
        .toUpperCase();

      if (!code) {
        alert("Room Code enter karo");
        return;
      }

      window.location.href =
        window.location.pathname + "?room=" + code;
    };

  </script>

</body>
</html>
