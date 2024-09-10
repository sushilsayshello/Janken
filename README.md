# Janken

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Janken (Rock, Paper, Scissors)</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
            margin: 0;
        }

        .container {
            text-align: center;
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        h1 {
            color: #333;
        }

        .choices {
            margin: 20px 0;
        }

        .choices button {
            padding: 10px 20px;
            font-size: 18px;
            margin: 0 10px;
            cursor: pointer;
            border: none;
            border-radius: 5px;
            transition: background-color 0.3s ease;
        }

        .choices button:hover {
            background-color: #ddd;
        }

        .result {
            margin-top: 20px;
            font-size: 1.2em;
            color: #333;
        }

        .result span {
            font-weight: bold;
            color: #007bff;
        }

        .outcome {
            font-size: 1.5em;
            margin-top: 10px;
            color: #007bff;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Janken Game (Rock, Paper, Scissors)</h1>
        <p>Choose your move:</p>
        <div class="choices">
            <button onclick="playGame('rock')">Rock</button>
            <button onclick="playGame('paper')">Paper</button>
            <button onclick="playGame('scissors')">Scissors</button>
        </div>
        <div class="result">
            <p>You chose: <span id="playerChoice">-</span></p>
            <p>Computer chose: <span id="computerChoice">-</span></p>
            <p class="outcome" id="outcome">-</p>
        </div>
    </div>

    <script>
        function playGame(playerChoice) {
            const choices = ['rock', 'paper', 'scissors'];
            const computerChoice = choices[Math.floor(Math.random() * choices.length)];

            document.getElementById('playerChoice').textContent = playerChoice;
            document.getElementById('computerChoice').textContent = computerChoice;

            let outcome = '';
            if (playerChoice === computerChoice) {
                outcome = "It's a tie!";
            } else if (
                (playerChoice === 'rock' && computerChoice === 'scissors') ||
                (playerChoice === 'paper' && computerChoice === 'rock') ||
                (playerChoice === 'scissors' && computerChoice === 'paper')
            ) {
                outcome = 'You win!';
            } else {
                outcome = 'You lose!';
            }

            document.getElementById('outcome').textContent = outcome;
        }
    </script>
</body>
</html>
