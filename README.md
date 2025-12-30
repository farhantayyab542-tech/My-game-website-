<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>2D Fighting Game - Advanced</title>
<style>
body { margin:0; background:#111; color:white; font-family:Arial; text-align:center; }
canvas { background:#222; display:block; margin:20px auto; border:2px solid #fff; }
#menu, #mobileControls { margin-top:10px; }
button { padding:10px 20px; margin:5px; font-size:16px; cursor:pointer; }
#mobileControls { display:none; }
</style>
</head>
<body>

<h1>2D Fighting Game</h1>
<div id="menu">
<button onclick="startGame()">Start Game</button>
</div>

<canvas id="game" width="600" height="300"></canvas>

<div id="mobileControls">
<h3>Player 1 Controls</h3>
<button onclick="pressKey('w')">↑</button>
<button onclick="pressKey('a')">←</button>
<button onclick="pressKey('s')">↓</button>
<button onclick="pressKey('d')">→</button>
<button onclick="pressKey('f')">Punch</button>
<button onclick="pressKey('g')">Kick</button>
<hr>
<h3>Player 2 Controls</h3>
<button onclick="pressKey('ArrowUp')">↑</button>
<button onclick="pressKey('ArrowLeft')">←</button>
<button onclick="pressKey('ArrowDown')">↓</button>
<button onclick="pressKey('ArrowRight')">→</button>
<button onclick="pressKey('k')">Punch</button>
<button onclick="pressKey('l')">Kick</button>
</div>

<script>
// Canvas
const canvas = document.getElementById("game");
const ctx = canvas.getContext("2d");

// Players
let player1, player2, gameInterval, keys = {};
let gameRunning = false;

function startGame() {
    player1 = {x:50, y:200, w:40, h:60, color:"red", health:100, action:"idle"};
    player2 = {x:510, y:200, w:40, h:60, color:"blue
