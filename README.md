- 👋 Hi, I’m @envixity1236
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
envixity1236/envixity1236 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
score = 0
playerX = 0
playerY = 0
enemyX = 10
enemyY = 10

// Game loop
while gameRunning:
  // Handle user input
  if keyPress("left"):
    playerX -= 5
  if keyPress("right"):
    playerX += 5
  if keyPress("up"):
    playerY -= 5
  if keyPress("down"):
    playerY += 5

  // Update game state
  if playerX == enemyX and playerY == enemyY:
    score += 1
    enemyX = random(0, screenWidth)
    enemyY = random(0, screenHeight)

  // Render game
  clearScreen()
  drawPlayer(playerX, playerY)
  drawEnemy(enemyX, enemyY)
  drawScore(score)
  updateScreen()

  // Check for game over
  if score >= 10:
    gameRunning = false
    showGameOverScreen()
