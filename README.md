# Janken

<details>
  <summary>Click to play Rock, Paper, Scissors!</summary>
  <div style="text-align: center; font-family: Arial, sans-serif;">
    <h1>Rock, Paper, Scissors Game</h1>
    <p>Choose Rock, Paper, or Scissors:</p>
    <button onclick="play('rock')">Rock</button>
    <button onclick="play('paper')">Paper</button>
    <button onclick="play('scissors')">Scissors</button>
    <div id="result" style="margin-top: 20px; font-size: 1.2em;"></div>
  </div>

  <script>
    function play(playerChoice) {
      const choices = ['rock', 'paper', 'scissors'];
      const computerChoice = choices[Math.floor(Math.random() * choices.length)];
      let result = '';

      if (playerChoice === computerChoice) {
        result = 'It\'s a tie!';
      } else if (
        (playerChoice === 'rock' && computerChoice === 'scissors') ||
        (playerChoice === 'paper' && computerChoice === 'rock') ||
        (playerChoice === 'scissors' && computerChoice === 'paper')
      ) {
        result = 'You win!';
      } else {
        result = 'You lose!';
      }

      document.getElementById('result').innerHTML = `
        You chose <strong>${playerChoice}</strong>.<br>
        The computer chose <strong>${computerChoice}</strong>.<br>
        <strong>${result}</strong>
      `;
    }
  </script>
</details>
