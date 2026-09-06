<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Skill Game</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #111;
      color: white;
      text-align: center;
    }

    .box {
      max-width: 400px;
      margin: 80px auto;
      padding: 25px;
    }

    h1 {
      font-size: 36px;
      margin-bottom: 10px;
    }

    p {
      color: #bbb;
    }

    button {
      width: 100%;
      padding: 16px;
      margin-top: 15px;
      border: 0;
      border-radius: 10px;
      font-size: 18px;
      font-weight: bold;
      cursor: pointer;
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
      width: 90%;
      padding: 14px;
      margin-top: 20px;
      border-radius: 8px;
      border: 1px solid #555;
      background: #222;
      color: white;
      font-size: 17px;
      text-align: center;
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
  </div>

  <script>
    document.getElementById("create").onclick = function () {
      alert("Create Room system coming next!");
    };

    document.getElementById("join").onclick = function () {
      const code = document.getElementById("roomCode").value.trim();

      if (!code) {
        alert("Room Code enter karo");
        return;
      }

      alert("Joining room: " + code);
    };
  </script>

</body>
</html>
