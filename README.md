<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Productive Daily Routine Game</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f4f4f4;
      margin: 0;
      padding: 20px;
    }
    .game-container {
      background-color: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      max-width: 400px;
      margin: 0 auto;
    }
    h1 {
      color: #333;
    }
    .task {
      margin: 10px 0;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
      background-color: #f9f9f9;
      cursor: pointer;
    }
    .task.completed {
      background-color: #d4edda;
      text-decoration: line-through;
    }
    .score {
      margin-top: 20px;
      font-size: 18px;
      color: #333;
    }
    button {
      padding: 10px 20px;
      font-size: 16px;
      background-color: #28a745;
      color: #fff;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      margin-top: 20px;
    }
    button:hover {
      background-color: #218838;
    }
  </style>
</head>
<body>
  <div class="game-container">
    <h1>Productive Daily Routine Game</h1>
    <p>Complete your daily tasks to build a productive routine!</p>
    <div id="tasks">
      <div class="task" data-task="exercise">🏋️‍♂️ Exercise for 30 minutes</div>
      <div class="task" data-task="work">💻 Work on important tasks</div>
      <div class="task" data-task="meditate">🧘‍♂️ Meditate for 10 minutes</div>
      <div class="task" data-task="break">☕ Take a 5-minute break</div>
      <div class="task" data-task="read">📚 Read for 20 minutes</div>
    </div>
    <div class="score">Score: <span id="score">0</span></div>
    <button onclick="resetGame()">Reset Game</button>
  </div>

  <script>
    let score = 0;
    const tasks = document.querySelectorAll('.task');
    const scoreElement = document.getElementById('score');

    tasks.forEach(task => {
      task.addEventListener('click', () => {
        if (!task.classList.contains('completed')) {
          task.classList.add('completed');
          score += 10; // Add 10 points for each completed task
          scoreElement.textContent = score;
          if (score === 50) {
            alert('🎉 Great job! You completed your productive routine!');
          }
        }
      });
    });

    function resetGame() {
      tasks.forEach(task => task.classList.remove('completed'));
      score = 0;
      scoreElement.textContent = score;
    }
  </script>
</body>
</html>
