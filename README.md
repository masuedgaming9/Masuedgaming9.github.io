# Masuedgaming9.github.io

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#080711">
<title>Game Space — Masud Gaming 9</title>

<style>
:root {
  --bg:#080711;
  --panel:#141126;
  --purple:#b44cff;
  --blue:#35d8ff;
  --pink:#ff4fd8;
  --text:#f5f3ff;
  --muted:#aaa6c7;
}
* { box-sizing:border-box; }
html { scroll-behavior:smooth; }
body {
  margin:0;
  background:radial-gradient(ellipse at top,#24103e,var(--bg) 55%);
  color:var(--text);
  font-family:system-ui,Arial,sans-serif;
}
a { color:var(--blue); text-decoration:none; }
button,input { font:inherit; }
button { cursor:pointer; }
.wrap { width:min(1100px,92%); margin:auto; }
header {
  position:sticky; top:0; z-index:10;
  background:#080711ed;
  border-bottom:1px solid #30284b;
  backdrop-filter:blur(12px);
}
nav {
  display:flex; justify-content:space-between;
  align-items:center; gap:12px; padding:17px 0;
}
.logo { font-size:22px; font-weight:950; }
.logo span { color:var(--blue); }
.logo b { color:var(--purple); }
.links { display:flex; gap:15px; flex-wrap:wrap; }
.links a { color:var(--muted); font-size:14px; }
.hero {
  padding:55px 0 35px;
  display:grid; grid-template-columns:1.2fr .8fr;
  gap:25px; align-items:center;
}
.eyebrow { color:var(--blue); letter-spacing:3px; font-size:12px; }
h1 { font-size:clamp(42px,7vw,78px); line-height:.98; margin:15px 0; }
h1 span { color:var(--purple); }
p { line-height:1.65; color:var(--muted); }
.hero-art {
  min-height:250px; display:grid; place-items:center;
  border:1px solid #65408b; border-radius:24px;
  background:linear-gradient(135deg,#241039,#081c35);
  box-shadow:0 0 35px #8e39ff22;
}
.planet {
  width:130px; height:130px; border-radius:50%;
  display:grid; place-items:center; font-size:45px;
  background:radial-gradient(circle at 35% 30%,#fff,#bd4cff 25%,#25206e 70%);
  box-shadow:0 0 50px #a044ff;
}
.btn {
  display:inline-block; padding:11px 15px; margin:4px 4px 4px 0;
  border:1px solid #42335e; border-radius:10px;
  color:white; background:#19152b;
}
.btn.primary {
  background:linear-gradient(100deg,#8839dc,#286de9);
  border-color:var(--purple);
}
section { padding:25px 0 35px; }
h2 { font-size:29px; margin:8px 0 18px; }
.tools { display:flex; gap:8px; flex-wrap:wrap; margin-bottom:18px; }
input {
  min-width:0; flex:1; padding:12px;
  color:white; background:#111020;
  border:1px solid #3b3055; border-radius:9px;
}
.filter { color:var(--muted); }
.filter.active { border-color:var(--purple); color:white; }
.grid {
  display:grid; grid-template-columns:repeat(3,minmax(0,1fr));
  gap:15px;
}
.card,.panel {
  overflow:hidden; border:1px solid #30284b;
  border-radius:15px; background:var(--panel);
}
.cover {
  height:120px; display:grid; place-items:center;
  font-size:48px;
  background:linear-gradient(135deg,#17375c,#37164e);
}
.card:nth-child(3n+2) .cover {
  background:linear-gradient(135deg,#411748,#181743);
}
.card:nth-child(3n) .cover {
  background:linear-gradient(135deg,#114a48,#171638);
}
.card-body { padding:14px; }
.card h3 { margin:0; }
.card-body p { font-size:14px; min-height:45px; }
.tag { color:var(--blue); font-size:11px; }
.arcade {
  display:grid; grid-template-columns:repeat(3,minmax(0,1fr));
  gap:15px;
}
.panel { padding:15px; }
.panel h3 { margin-top:0; }
.screen {
  min-height:170px; margin:12px 0; padding:12px;
  display:grid; place-items:center;
  background:#080711; border:1px solid #34264c;
  border-radius:10px;
}
.status { color:#63ffb2; font-size:13px; }
#snakeCanvas {
  width:100%; max-width:240px; height:auto;
  background:#05060b; touch-action:none;
}
.dpad {
  display:grid; grid-template-columns:repeat(3,38px);
  gap:4px; justify-content:center; margin-top:8px;
}
.dpad button {
  background:#211735; color:white;
  border:1px solid #493564; border-radius:6px; padding:6px;
}
.dpad button:nth-child(1) { grid-column:2; }
.dpad button:nth-child(2) { grid-column:1; }
.dpad button:nth-child(3) { grid-column:2; grid-row:2; }
.dpad button:nth-child(4) { grid-column:3; grid-row:2; }
.ttt { display:grid; grid-template-columns:repeat(3,55px); gap:5px; }
.ttt button {
  height:55px; color:var(--blue); font-size:25px;
  background:#19152b; border:1px solid #493564;
  border-radius:8px;
}
.clicker {
  width:100%; min-height:130px; color:white;
  font-weight:bold; font-size:18px;
  background:radial-gradient(circle,#39215e,#111020);
  border:1px solid var(--purple); border-radius:12px;
}
.clicker strong { display:block; color:var(--blue); font-size:40px; }
footer {
  border-top:1px solid #30284b;
  padding:25px 0; color:var(--muted); font-size:13px;
}
.small { font-size:12px; }
@media(max-width:750px) {
  .hero { grid-template-columns:1fr; padding-top:35px; }
  .hero-art { min-height:190px; }
  .grid,.arcade { grid-template-columns:repeat(2,minmax(0,1fr)); }
}
@media(max-width:500px) {
  nav { align-items:flex-start; }
  .links { gap:8px; }
  .links a { font-size:12px; }
  .grid,.arcade { grid-template-columns:1fr; }
}
</style>
</head>

<body>
<header>
  <div class="wrap">
    <nav>
      <a class="logo" href="#">◈ <span>GAME</span><b> SPACE</b></a>
      <div class="links">
        <a href="#library">Library</a>
        <a href="#mygames">My Games</a>
        <a href="#arcade">Play</a>
        <a href="#about">About</a>
      </div>
    </nav>
  </div>
</header>

<main class="wrap">
  <section class="hero">
    <div>
      <div class="eyebrow">YOUR NEON ARCADE</div>
      <h1>ENTER THE<br><span>GAME SPACE</span></h1>
      <p>Your gaming world. Discover games, save favourites,
      keep a personal list of phone games and play mini-games
      directly in your browser.</p>
      <a class="btn primary" href="#arcade">▶ PLAY NOW</a>
      <a class="btn" href="#library">EXPLORE GAMES</a>
    </div>
    <div class="hero-art">
      <div class="planet">✦</div>
    </div>
  </section>

  <section id="library">
    <div class="eyebrow">01 // DISCOVER</div>
    <h2>Game Library</h2>

    <div class="tools">
      <input id="search" placeholder="Search games...">
      <button class="btn filter active" data-filter="All">All</button>
      <button class="btn filter" data-filter="Arcade">Arcade</button>
      <button class="btn filter" data-filter="Racing">Racing</button>
      <button class="btn filter" data-filter="Action">Action</button>
      <button class="btn filter" data-filter="Favorites">♥ Saved</button>
    </div>

    <div class="grid" id="gameGrid">
      <article class="card" data-name="Neon Snake" data-category="Arcade">
        <div class="cover">🐍</div>
        <div class="card-body">
          <span class="tag">ARCADE</span><h3>Neon Snake</h3>
          <p>Collect glowing energy and avoid crashing into yourself.</p>
          <a class="btn primary" href="#snake">Play now</a>
          <button class="btn fav" aria-label="Save Neon Snake">♡</button>
        </div>
      </article>

      <article class="card" data-name="Cyber Tic-Tac-Toe" data-category="Arcade">
        <div class="cover">✕ ◯</div>
        <div class="card-body">
          <span class="tag">PUZZLE</span><h3>Cyber Tic-Tac-Toe</h3>
          <p>Get three marks in a row to win.</p>
          <a class="btn primary" href="#tictactoe">Play now</a>
          <button class="btn fav" aria-label="Save Tic-Tac-Toe">♡</button>
        </div>
      </article>

      <article class="card" data-name="Pulse Clicker" data-category="Arcade">
        <div class="cover">⚡</div>
        <div class="card-body">
          <span class="tag">CLICKER</span><h3>Pulse Clicker</h3>
          <p>Tap the energy core as fast as you can.</p>
          <a class="btn primary" href="#clicker">Play now</a>
          <button class="btn fav" aria-label="Save Pulse Clicker">♡</button>
        </div>
      </article>

      <article class="card" data-name="Asphalt Legends Unite" data-category="Racing">
        <div class="cover">🏎️</div>
        <div class="card-body">
          <span class="tag">RACING</span><h3>Asphalt Legends Unite</h3>
          <p>Explore arcade racing and high-speed cars.</p>
          <a class="btn" href="https://asphaltlegends.com/" target="_blank" rel="noopener">Official site ↗</a>
          <button class="btn fav" aria-label="Save Asphalt Legends">♡</button>
        </div>
      </article>

      <article class="card" data-name="Brawlhalla" data-category="Action">
        <div class="cover">⚔️</div>
        <div class="card-body">
          <span class="tag">ACTION</span><h3>Brawlhalla</h3>
          <p>A platform fighting game with online battles.</p>
          <a class="btn" href="https://www.brawlhalla.com/" target="_blank" rel="noopener">Official site ↗</a>
          <button class="btn fav" aria-label="Save Brawlhalla">♡</button>
        </div>
      </article>

      <article class="card" data-name="Trackmania" data-category="Racing">
        <div class="cover">🏁</div>
        <div class="card-body">
          <span class="tag">RACING</span><h3>Trackmania</h3>
          <p>Race against the clock on precision tracks.</p>
          <a class="btn" href="https://www.trackmania.com/" target="_blank" rel="noopener">Official site ↗</a>
          <button class="btn fav" aria-label="Save Trackmania">♡</button>
        </div>
      </article>
    </div>
    <p class="small">External games open their official websites. Their availability and pricing may vary.</p>
  </section>

  <section id="mygames">
    <div class="eyebrow">02 // YOUR DEVICE</div>
    <h2>My Phone Games</h2>
    <div class="panel">
      <p>Add games installed on your Android phone to your personal list.
      A website cannot automatically scan installed apps.</p>
      <form id="phoneForm" class="tools">
        <input id="phoneName" placeholder="Game name" required>
        <input id="phonePackage" placeholder="Optional Android package ID">
        <button class="btn primary" type="submit">＋ Add game</button>
      </form>
      <div id="phoneList" class="grid"></div>
      <p class="small">Launching a phone game from a browser is not guaranteed to work.</p>
    </div>
  </section>

  <section id="arcade">
    <div class="eyebrow">03 // INSERT COIN</div>
    <h2>Mini Arcade</h2>
    <div class="arcade">

      <div class="panel" id="snake">
        <h3>🐍 Neon Snake</h3>
        <p>Collect the dots. Use the arrows below.</p>
        <div class="screen">
          <div style="width:100%;text-align:center">
            <canvas id="snakeCanvas" width="240" height="240"></canvas>
            <div class="dpad">
              <button data-dir="up">▲</button>
              <button data-dir="left">◀</button>
              <button data-dir="down">▼</button>
              <button data-dir="right">▶</button>
            </div>
            <div class="status" id="snakeStatus">Press Start</div>
          </div>
        </div>
        <button class="btn primary" id="snakeStart">▶ Start / Restart</button>
        <button class="btn" id="snakePause">Ⅱ Pause</button>
      </div>

      <div class="panel" id="tictactoe">
        <h3>✕ Cyber Tic-Tac-Toe</h3>
        <p>Two players, one phone. X goes first.</p>
        <div class="screen">
          <div>
            <div class="ttt" id="tttBoard"></div>
            <div class="status" id="tttStatus">Your move: X</div>
          </div>
        </div>
        <button class="btn primary" id="tttReset">↻ New round</button>
      </div>

      <div class="panel" id="clicker">
        <h3>⚡ Pulse Clicker</h3>
        <p>Tap the core as often as possible in 10 seconds.</p>
        <div class="screen">
          <button class="clicker" id="clickTarget" disabled>
            TAP! <strong id="clickScore">0</strong>
            <span id="clickLabel">Press Start below</span>
          </button>
        </div>
        <button class="btn primary" id="clickStart">▶ Start 10s round</button>
        <div class="status" id="clickStatus">Best score: 0</div>
      </div>

    </div>
  </section>

  <section id="about">
    <div class="eyebrow">04 // ABOUT</div>
    <h2>Your Space. Your Rules.</h2>
    <div class="panel">
      <p>Game Space is a cyberpunk gaming website developed by
      <strong style="color:var(--blue)">Masud Gaming 9</strong>.</p>
      <p>Built with HTML, CSS and JavaScript. Designed for mobile
      and desktop, with no paid libraries. You can host it using
      the free GitHub Pages plan.</p>
    </div>
  </section>
</main>

<footer>
  <div class="wrap">
    ◈ GAME SPACE // NEON ARCADE<br><br>
    Developed by <strong style="color:var(--blue)">Masud Gaming 9</strong>
  </div>
</footer>

<script>
(() => {
  const $ = s => document.querySelector(s);
  const $$ = s => [...document.querySelectorAll(s)];

  // GAME LIBRARY: search, filters and favourites
  let filter = "All";
  let favourites = [];
  let phoneGames = [];

  try {
    favourites = JSON.parse(localStorage.getItem("gs-favs") || "[]");
    phoneGames = JSON.parse(localStorage.getItem("gs-phone-games") || "[]");
  } catch (e) {}

  const cards = $$(".card");

  function updateLibrary() {
    const query = $("#search").value.toLowerCase().trim();

    cards.forEach(card => {
      const name = card.dataset.name;
      const matchesText = (name + " " + card.innerText)
        .toLowerCase().includes(query);
      const matchesFilter =
        filter === "All" ||
        (filter === "Favorites" && favourites.includes(name)) ||
        card.dataset.category === filter;

      card.style.display = matchesText && matchesFilter ? "" : "none";

      const button = card.querySelector(".fav");
      const saved = favourites.includes(name);
      button.textContent = saved ? "♥" : "♡";
      button.style.color = saved ? "#ff4fd8" : "";
    });
  }

  $$(".filter").forEach(button => {
    button.addEventListener("click", () => {
      filter = button.dataset.filter;
      $$(".filter").forEach(b => b.classList.toggle("active", b === button));
      updateLibrary();
    });
  });

  $("#search").addEventListener("input", updateLibrary);

  $$(".fav").forEach(button => {
    button.addEventListener("click", () => {
      const name = button.closest(".card").dataset.name;
      favourites = favourites.includes(name)
        ? favourites.filter(x => x !== name)
        : [...favourites, name];

      try { localStorage.setItem("gs-favs", JSON.stringify(favourites)); }
      catch (e) {}
      updateLibrary();
    });
  });

  updateLibrary();

  // PHONE GAME LIST: manually add games
  function renderPhoneGames() {
    const list = $("#phoneList");
    list.innerHTML = "";

    if (!phoneGames.length) {
      list.textContent = "Your list is empty. Add a game above.";
      return;
    }

    phoneGames.forEach((game, index) => {
      const card = document.createElement("div");
      card.className = "panel";

      const title = document.createElement("h3");
      title.textContent = "🎮 " + game.name;
      card.append(title);

      const info = document.createElement("p");
      info.textContent = game.pkg || "Package ID not provided";
      card.append(info);

      if (game.pkg) {
        const launch = document.createElement("button");
        launch.className = "btn primary";
        launch.textContent = "▶ Try open";
        launch.addEventListener("click", () => {
          if (!/^[\w]+(\.[\w]+)+$/.test(game.pkg)) {
            alert("Please check the Android package ID.");
            return;
          }
          location.href =
            "intent://#Intent;action=android.intent.action.MAIN;" +
            "category=android.intent.category.LAUNCHER;package=" +
            game.pkg + ";end";
        });
        card.append(launch);
      }

      const remove = document.createElement("button");
      remove.className = "btn";
      remove.textContent = "Remove";
      remove.addEventListener("click", () => {
        phoneGames.splice(index, 1);
        savePhoneGames();
        renderPhoneGames();
      });
      card.append(remove);
      list.append(card);
    });
  }

  function savePhoneGames() {
    try {
      localStorage.setItem("gs-phone-games", JSON.stringify(phoneGames));
    } catch (e) {}
  }

  $("#phoneForm").addEventListener("submit", event => {
    event.preventDefault();

    const name = $("#phoneName").value.trim();
    const pkg = $("#phonePackage").value.trim();

    if (!name) return;
    if (phoneGames.some(g => g.name.toLowerCase() === name.toLowerCase())) {
      alert("That game is already in your list.");
      return;
    }

    phoneGames.push({ name, pkg });
    savePhoneGames();
    renderPhoneGames();
    $("#phoneForm").reset();
  });

  renderPhoneGames();

  // TIC-TAC-TOE
  let cells = Array(9).fill("");
  let turn = "X";
  let finished = false;

  function winner() {
    const lines = [
      [0,1,2],[3,4,5],[6,7,8],
      [0,3,6],[1,4,7],[2,5,8],
      [0,4,8],[2,4,6]
    ];

    for (const line of lines) {
      const [a,b,c] = line;
      if (cells[a] && cells[a] === cells[b] && cells[b] === cells[c]) {
        return cells[a];
      }
    }

    return cells.every(Boolean) ? "Draw" : "";
  }

  function drawBoard() {
    const board = $("#tttBoard");
    board.innerHTML = "";

    cells.forEach((value, index) => {
      const button = document.createElement("button");
      button.textContent = value;
      button.disabled = !!value || finished;

      button.addEventListener("click", () => {
        if (finished || cells[index]) return;

        cells[index] = turn;
        const result = winner();

        if (result) {
          finished = true;
          $("#tttStatus").textContent =
            result === "Draw" ? "It's a draw!" : result + " wins!";
        } else {
          turn = turn === "X" ? "O" : "X";
          $("#tttStatus").textContent = "Your move: " + turn;
        }

        drawBoard();
      });

      board.append(button);
    });
  }

  $("#tttReset").addEventListener("click", () => {
    cells = Array(9).fill("");
    turn = "X";
    finished = false;
    $("#tttStatus").textContent = "Your move: X";
    drawBoard();
  });

  drawBoard();

  // PULSE CLICKER
  let score = 0;
  let best = 0;
  let seconds = 10;
  let timer = null;
  let running = false;

  try {
    best = Number(localStorage.getItem("gs-best") || 0);
  } catch (e) {}

  function updateClicker() {
    $("#clickScore").textContent = score;
    $("#clickLabel").textContent = running
      ? seconds + " seconds left"
      : seconds === 0 ? "Round over!" : "Press Start below";

    $("#clickTarget").disabled = !running;
    $("#clickStatus").textContent = "Best score: " + best;
  }

  $("#clickStart").addEventListener("click", () => {
    clearInterval(timer);
    score = 0;
    seconds = 10;
    running = true;
    updateClicker();

    timer = setInterval(() => {
      seconds--;

      if (seconds <= 0) {
        seconds = 0;
        running = false;
        clearInterval(timer);

        if (score > best) {
          best = score;
          try { localStorage.setItem("gs-best", best); } catch (e) {}
        }
      }

      updateClicker();
    }, 1000);
  });

  $("#clickTarget").addEventListener("click", () => {
    if (!running) return;
    score++;
    updateClicker();
  });

  updateClicker();

  // NEON SNAKE
  const canvas = $("#snakeCanvas");
  const ctx = canvas.getContext("2d");
  const size = 16;
  const cellsCount = 15;

  let snake = [];
  let food = {x:10,y:7};
  let direction = {x:1,y:0};
  let nextDirection = {x:1,y:0};
  let snakeScore = 0;
  let snakeTimer = null;
  let paused = true;
  let gameOver = false;

  function newFood() {
    let point;
    do {
      point = {
        x: Math.floor(Math.random() * cellsCount),
        y: Math.floor(Math.random() * cellsCount)
      };
    } while (snake.some(p => p.x === point.x && p.y === point.y));

    return point;
  }

  function drawSnake() {
    ctx.fillStyle = "#05060b";
    ctx.fillRect(0, 0, 240, 240);

    ctx.strokeStyle = "#17152b";
    for (let i = 0; i <= cellsCount; i++) {
      ctx.beginPath();
      ctx.moveTo(i * size, 0);
      ctx.lineTo(i * size, 240);
      ctx.stroke();

      ctx.beginPath();
      ctx.moveTo(0, i * size);
      ctx.lineTo(240, i * size);
      ctx.stroke();
    }

    ctx.fillStyle = "#35d8ff";
    ctx.shadowColor = "#35d8ff";
    ctx.shadowBlur = 12;
    ctx.beginPath();
    ctx.arc(food.x * size + 8, food.y * size + 8, 5, 0, Math.PI * 2);
    ctx.fill();
    ctx.shadowBlur = 0;

    snake.forEach((point, index) => {
      ctx.fillStyle = index === 0 ? "#ffffff" : "#63ffb2";
      ctx.fillRect(point.x * size + 2, point.y * size + 2, 12, 12);
    });

    if (paused && !gameOver) {
      ctx.fillStyle = "white";
      ctx.font = "bold 13px system-ui";
      ctx.textAlign = "center";
      ctx.fillText("PRESS START", 120, 120);
    }

    if (gameOver) {
      ctx.fillStyle = "#ff4fd8";
      ctx.font = "bold 17px system-ui";
      ctx.textAlign = "center";
      ctx.fillText("GAME OVER", 120, 120);
    }
  }

  function startSnake() {
    clearInterval(snakeTimer);

    snake = [{x:7,y:7},{x:6,y:7},{x:5,y:7}];
    direction = {x:1,y:0};
    nextDirection = {x:1,y:0};
    snakeScore = 0;
    food = newFood();
    paused = false;
    gameOver = false;

    $("#snakeStatus").textContent = "Score: 0";
    $("#snakePause").textContent = "Ⅱ Pause";
    drawSnake();
    snakeTimer = setInterval(tickSnake, 145);
  }

  function tickSnake() {
    if (paused || gameOver) return;

    direction = nextDirection;

    const head = {
      x: snake[0].x + direction.x,
      y: snake[0].y + direction.y
    };

    if (
      head.x < 0 || head.x >= cellsCount ||
      head.y < 0 || head.y >= cellsCount ||
      snake.some((p, i) => i > 0 && p.x === head.x && p.y === head.y)
    ) {
      gameOver = true;
      clearInterval(snakeTimer);
      $("#snakeStatus").textContent = "Game over! Score: " + snakeScore;
      drawSnake();
      return;
    }

    snake.unshift(head);

    if (head.x === food.x && head.y === food.y) {
      snakeScore++;
      food = newFood();
      $("#snakeStatus").textContent = "Score: " + snakeScore;
    } else {
      snake.pop();
    }

    drawSnake();
  }

  function setDirection(name) {
    const directions = {
      up:{x:0,y:-1}, down:{x:0,y:1},
      left:{x:-1,y:0}, right:{x:1,y:0}
    };

    const d = directions[name];
    if (!d) return;
    if (d.x === -direction.x && d.y === -direction.y) return;
    nextDirection = d;
  }

  $("#snakeStart").addEventListener("click", startSnake);

  $("#snakePause").addEventListener("click", () => {
    if (!snake.length || gameOver) return;
    paused = !paused;
    $("#snakePause").textContent = paused ? "▶ Resume" : "Ⅱ Pause";
    drawSnake();
  });

  $$("[data-dir]").forEach(button => {
    button.addEventListener("click", () => setDirection(button.dataset.dir));
  });

  document.addEventListener("keydown", event => {
    const keys = {
      ArrowUp:"up", ArrowDown:"down",
      ArrowLeft:"left", ArrowRight:"right",
      w:"up", s:"down", a:"left", d:"right"
    };

    if (keys[event.key] && document.activeElement.tagName !== "INPUT") {
      setDirection(keys[event.key]);
    }
  });

  snake = [{x:7,y:7},{x:6,y:7},{x:5,y:7}];
  drawSnake();
})();
</script>
</body>
</html>

