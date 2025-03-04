#<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Secret Message Puzzle</title>
    <style>
        body {
            background-color: #ffccdc;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            text-align: center;
            font-family: Arial, sans-serif;
        }
        .message {
            font-size: 24px;
            font-weight: bold;
            color: #d147a3;
            display: none;
            margin-top: 20px;
            animation: fadeIn 1s ease-in-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.8); }
            to { opacity: 1; transform: scale(1); }
        }
        .puzzle {
            font-size: 18px;
            margin-top: 20px;
        }
        .input-box {
            padding: 10px;
            font-size: 16px;
            margin-top: 10px;
            border: 2px solid #d147a3;
            border-radius: 5px;
        }
        .submit-btn {
            background-color: #d147a3;
            color: white;
            padding: 10px 20px;
            font-size: 18px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <h1>Hey, solve all 10 puzzles to see the secret! 🧩</h1>
    <div class="puzzle" id="puzzleText">Loading puzzle...</div>
    <input type="number" id="answer" class="input-box" placeholder="Your answer">
    <button class="submit-btn" onclick="checkAnswer()">Submit</button>
    <div class="message" id="secretMessage">Loved your Intelligence 💖</div>
    
    <script>
        const puzzles = [
            { question: "What is 5 + 3?", answer: 8 },
            { question: "What is 10 - 4?", answer: 6 },
            { question: "What is 6 x 2?", answer: 12 },
            { question: "What is 9 / 3?", answer: 3 },
            { question: "What is 15 - 5?", answer: 10 },
            { question: "What is 7 + 8?", answer: 15 },
            { question: "What is 20 / 4?", answer: 5 },
            { question: "What is 3 x 5?", answer: 15 },
            { question: "What is 18 - 9?", answer: 9 },
            { question: "What is 12 + 4?", answer: 16 }
        ];
        
        let currentPuzzle = 0;
        
        function loadPuzzle() {
            document.getElementById("puzzleText").innerText = puzzles[currentPuzzle].question;
        }
        
        function checkAnswer() {
            const userAnswer = document.getElementById("answer").value;
            if (parseInt(userAnswer) === puzzles[currentPuzzle].answer) {
                currentPuzzle++;
                if (currentPuzzle < puzzles.length) {
                    loadPuzzle();
                    document.getElementById("answer").value = "";
                } else {
                    document.getElementById("secretMessage").style.display = "block";
                }
            } else {
                alert("Oops! Try again.");
            }
        }
        
        loadPuzzle();
    </script>
</body>
</html> Secret-Message
