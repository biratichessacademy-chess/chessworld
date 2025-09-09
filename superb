<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Birati Chess Academy - Mobile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-touch-callout: none;
            -webkit-user-select: none;
            user-select: none;
        }
        
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #4a90e2 0%, #357abd 100%);
            min-height: 100vh;
            padding: 10px;
            overflow-x: hidden;
        }
        
        .container {
            background: white;
            border-radius: 15px;
            padding: 15px;
            max-width: 100%;
            margin: 0 auto;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }
        
        h1 {
            text-align: center;
            color: #2c3e50;
            font-size: 1.5em;
            margin-bottom: 5px;
            font-weight: bold;
        }
        
        h2 {
            text-align: center;
            color: #3498db;
            font-size: 1.2em;
            margin-bottom: 20px;
        }
        
        .mode-buttons {
            display: flex;
            gap: 8px;
            margin-bottom: 20px;
            flex-wrap: wrap;
            justify-content: center;
        }
        
        .mode-btn {
            padding: 12px 16px;
            border: none;
            border-radius: 25px;
            font-size: 14px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            background: #3498db;
            color: white;
            flex: 1;
            min-width: 100px;
            max-width: 150px;
        }
        
        .mode-btn:active {
            transform: scale(0.95);
        }
        
        .mode-btn.active {
            background: #27ae60;
        }
        
        .game-area {
            min-height: 300px;
            text-align: center;
        }
        
        .chessboard {
            display: grid;
            grid-template-columns: repeat(8, 1fr);
            grid-template-rows: repeat(8, 1fr);
            gap: 1px;
            max-width: 320px;
            margin: 15px auto;
            border: 3px solid #2c3e50;
            border-radius: 8px;
            background: #2c3e50;
            aspect-ratio: 1;
        }
        
        .square {
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: clamp(20px, 5vw, 28px);
            cursor: pointer;
            transition: all 0.2s ease;
            aspect-ratio: 1;
        }
        
        .square.light {
            background-color: #f0d9b5;
        }
        
        .square.dark {
            background-color: #b58863;
        }
        
        .square:active {
            transform: scale(0.9);
        }
        
        .square.highlight {
            background-color: #ffeb3b !important;
            animation: pulse 1s infinite;
        }
        
        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }
        
        .piece-info {
            background: #ecf0f1;
            border-radius: 12px;
            padding: 15px;
            margin: 15px 0;
            text-align: center;
        }
        
        .piece-info h3 {
            color: #2c3e50;
            margin-bottom: 10px;
            font-size: 1.3em;
        }
        
        .piece-info p {
            color: #34495e;
            font-size: 1em;
            line-height: 1.4;
        }
        
        .quiz-area {
            background: #e8f5e8;
            border-radius: 12px;
            padding: 20px;
            margin: 15px 0;
        }
        
        .quiz-question {
            font-size: 1.2em;
            color: #2c3e50;
            margin-bottom: 15px;
            font-weight: bold;
        }
        
        .piece-options {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
            margin-bottom: 15px;
        }
        
        .piece-option {
            background: white;
            border: 2px solid #bdc3c7;
            border-radius: 12px;
            padding: 15px;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s ease;
            min-height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
        }
        
        .piece-option:active {
            transform: scale(0.95);
        }
        
        .piece-option.correct {
            border-color: #27ae60;
            background: #d5f4e6;
        }
        
        .piece-option.wrong {
            border-color: #e74c3c;
            background: #fdeaea;
        }
        
        .score {
            font-size: 1.3em;
            color: #2c3e50;
            margin-bottom: 15px;
            font-weight: bold;
        }
        
        .feedback {
            font-size: 1.1em;
            font-weight: bold;
            margin: 15px 0;
            text-align: center;
            padding: 12px;
            border-radius: 8px;
        }
        
        .feedback.correct {
            background: #d5f4e6;
            color: #27ae60;
        }
        
        .feedback.wrong {
            background: #fdeaea;
            color: #e74c3c;
        }
        
        .next-btn {
            background: #27ae60;
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 25px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            margin: 10px;
        }
        
        .next-btn:active {
            transform: scale(0.95);
        }
        
        .move-dot {
            position: absolute;
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: #ffeb3b;
            border: 2px solid #f57f17;
            pointer-events: none;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>BIRATI CHESS ACADEMY</h1>
        <h2>🏰 Learn Chess! 🏰</h2>
        
        <div class="mode-buttons">
            <button class="mode-btn active" onclick="switchMode('learn')">📚 Learn</button>
            <button class="mode-btn" onclick="switchMode('quiz')">🧩 Quiz</button>
            <button class="mode-btn" onclick="switchMode('moves')">🏃 Moves</button>
        </div>
        
        <div class="game-area">
            <!-- Learn Mode -->
            <div id="learn-mode">
                <div class="piece-info">
                    <h3>Tap any chess piece to learn!</h3>
                    <p>Each piece moves differently. Discover their powers! 🎯</p>
                </div>
                <div class="chessboard" id="learn-board"></div>
                <div id="piece-description" class="piece-info" style="display: none;"></div>
            </div>
            
            <!-- Quiz Mode -->
            <div id="quiz-mode" style="display: none;">
                <div class="score">Score: <span id="quiz-score">0</span>/5 🌟</div>
                <div class="quiz-area">
                    <div class="quiz-question" id="quiz-question">Which piece is this?</div>
                    <div class="piece-options" id="piece-options"></div>
                    <div id="quiz-feedback" class="feedback" style="display: none;"></div>
                    <button class="next-btn" id="next-question" onclick="nextQuestion()" style="display: none;">Next</button>
                </div>
            </div>
            
            <!-- Moves Mode -->
            <div id="moves-mode" style="display: none;">
                <div class="piece-info">
                    <h3>Tap a piece to see its moves!</h3>
                    <p>Yellow dots show where it can go! ✨</p>
                </div>
                <div class="chessboard" id="moves-board"></div>
            </div>
        </div>
    </div>

    <script>
        const pieces = {
            '♔': { name: 'King', description: 'The most important piece! Moves one square in any direction.' },
            '♕': { name: 'Queen', description: 'The most powerful! Moves any direction, any distance.' },
            '♖': { name: 'Rook', description: 'The castle! Moves straight lines only.' },
            '♗': { name: 'Bishop', description: 'Moves diagonally any distance.' },
            '♘': { name: 'Knight', description: 'The horse! Moves in L-shape and jumps over pieces.' },
            '♙': { name: 'Pawn', description: 'The soldier! Moves forward, captures diagonally.' }
        };

        const board = [
            ['♜', '♞', '♝', '♛', '♚', '♝', '♞', '♜'],
            ['♟', '♟', '♟', '♟', '♟', '♟', '♟', '♟'],
            [null, null, null, null, null, null, null, null],
            [null, null, null, null, null, null, null, null],
            [null, null, null, null, null, null, null, null],
            [null, null, null, null, null, null, null, null],
            ['♙', '♙', '♙', '♙', '♙', '♙', '♙', '♙'],
            ['♖', '♘', '♗', '♕', '♔', '♗', '♘', '♖']
        ];

        let currentMode = 'learn';
        let quizScore = 0;
        let currentQuestion = 0;
        let quizQuestions = [];

        function createBoard(boardId) {
            const boardEl = document.getElementById(boardId);
            boardEl.innerHTML = '';
            
            for (let row = 0; row < 8; row++) {
                for (let col = 0; col < 8; col++) {
                    const square = document.createElement('div');
                    square.className = `square ${(row + col) % 2 === 0 ? 'light' : 'dark'}`;
                    square.dataset.row = row;
                    square.dataset.col = col;
                    
                    if (board[row][col]) {
                        square.textContent = board[row][col];
                        if (boardId === 'learn-board') {
                            square.onclick = () => showPieceInfo(board[row][col]);
                        } else if (boardId === 'moves-board') {
                            square.onclick = () => showMoves(row, col, board[row][col]);
                        }
                    }
                    
                    boardEl.appendChild(square);
                }
            }
        }

        function showPieceInfo(piece) {
            const whiteEquivalent = piece === '♜' ? '♖' : 
                                  piece === '♞' ? '♘' : 
                                  piece === '♝' ? '♗' : 
                                  piece === '♛' ? '♕' : 
                                  piece === '♚' ? '♔' : 
                                  piece === '♟' ? '♙' : piece;
            
            const info = pieces[whiteEquivalent];
            const description = document.getElementById('piece-description');
            
            description.innerHTML = `
                <h3>${piece} ${info.name}</h3>
                <p>${info.description}</p>
            `;
            description.style.display = 'block';
        }

        function showMoves(row, col, piece) {
            document.querySelectorAll('.move-dot').forEach(el => el.remove());
            document.querySelectorAll('.square').forEach(el => el.classList.remove('highlight'));
            
            const selectedSquare = document.querySelector(`#moves-board .square[data-row="${row}"][data-col="${col}"]`);
            selectedSquare.classList.add('highlight');
            
            const moves = getPossibleMoves(row, col, piece);
            moves.forEach(([moveRow, moveCol]) => {
                const targetSquare = document.querySelector(`#moves-board .square[data-row="${moveRow}"][data-col="${moveCol}"]`);
                if (targetSquare) {
                    const dot = document.createElement('div');
                    dot.className = 'move-dot';
                    targetSquare.style.position = 'relative';
                    targetSquare.appendChild(dot);
                }
            });
        }

        function getPossibleMoves(row, col, piece) {
            const moves = [];
            const whiteEquivalent = piece === '♜' ? '♖' : 
                                  piece === '♞' ? '♘' : 
                                  piece === '♝' ? '♗' : 
                                  piece === '♛' ? '♕' : 
                                  piece === '♚' ? '♔' : 
                                  piece === '♟' ? '♙' : piece;
            
            switch(whiteEquivalent) {
                case '♔': // King - one square any direction
                    for (let r = -1; r <= 1; r++) {
                        for (let c = -1; c <= 1; c++) {
                            if (r === 0 && c === 0) continue;
                            const newRow = row + r;
                            const newCol = col + c;
                            if (newRow >= 0 && newRow < 8 && newCol >= 0 && newCol < 8) {
                                moves.push([newRow, newCol]);
                            }
                        }
                    }
                    break;
                case '♖': // Rook - horizontal and vertical
                    for (let i = 1; i < 4; i++) { // Limit for mobile display
                        if (col + i < 8) moves.push([row, col + i]);
                        if (col - i >= 0) moves.push([row, col - i]);
                        if (row + i < 8) moves.push([row + i, col]);
                        if (row - i >= 0) moves.push([row - i, col]);
                    }
                    break;
                case '♗': // Bishop - diagonal
                    for (let i = 1; i < 4; i++) { // Limit for mobile display
                        if (row + i < 8 && col + i < 8) moves.push([row + i, col + i]);
                        if (row + i < 8 && col - i >= 0) moves.push([row + i, col - i]);
                        if (row - i >= 0 && col + i < 8) moves.push([row - i, col + i]);
                        if (row - i >= 0 && col - i >= 0) moves.push([row - i, col - i]);
                    }
                    break;
                case '♕': // Queen - combination (limited for mobile)
                    for (let i = 1; i < 3; i++) {
                        // Horizontal/Vertical
                        if (col + i < 8) moves.push([row, col + i]);
                        if (col - i >= 0) moves.push([row, col - i]);
                        if (row + i < 8) moves.push([row + i, col]);
                        if (row - i >= 0) moves.push([row - i, col]);
                        // Diagonal
                        if (row + i < 8 && col + i < 8) moves.push([row + i, col + i]);
                        if (row + i < 8 && col - i >= 0) moves.push([row + i, col - i]);
                        if (row - i >= 0 && col + i < 8) moves.push([row - i, col + i]);
                        if (row - i >= 0 && col - i >= 0) moves.push([row - i, col - i]);
                    }
                    break;
                case '♘': // Knight - L-shape
                    const knightMoves = [[-2,-1], [-2,1], [-1,-2], [-1,2], [1,-2], [1,2], [2,-1], [2,1]];
                    knightMoves.forEach(([r, c]) => {
                        const newRow = row + r;
                        const newCol = col + c;
                        if (newRow >= 0 && newRow < 8 && newCol >= 0 && newCol < 8) {
                            moves.push([newRow, newCol]);
                        }
                    });
                    break;
                case '♙': // Pawn - forward movement
                    if (piece === '♙') { // White pawn
                        if (row > 0) moves.push([row - 1, col]);
                    } else { // Black pawn
                        if (row < 7) moves.push([row + 1, col]);
                    }
                    break;
            }
            return moves;
        }

        function switchMode(mode) {
            document.querySelectorAll('.mode-btn').forEach(btn => btn.classList.remove('active'));
            event.target.classList.add('active');
            
            document.getElementById('learn-mode').style.display = 'none';
            document.getElementById('quiz-mode').style.display = 'none';
            document.getElementById('moves-mode').style.display = 'none';
            
            document.getElementById(mode + '-mode').style.display = 'block';
            currentMode = mode;
            
            if (mode === 'quiz') {
                startQuiz();
            } else if (mode === 'moves') {
                createBoard('moves-board');
            } else {
                createBoard('learn-board');
            }
        }

        function startQuiz() {
            quizScore = 0;
            currentQuestion = 0;
            document.getElementById('quiz-score').textContent = quizScore;
            
            quizQuestions = [];
            const pieceList = Object.keys(pieces);
            for (let i = 0; i < 5; i++) { // Shorter quiz for mobile
                const correctPiece = pieceList[Math.floor(Math.random() * pieceList.length)];
                quizQuestions.push({
                    piece: correctPiece,
                    options: getRandomOptions(correctPiece)
                });
            }
            
            showQuestion();
        }

        function getRandomOptions(correctPiece) {
            const allPieces = Object.keys(pieces);
            const options = [correctPiece];
            
            while (options.length < 4) {
                const randomPiece = allPieces[Math.floor(Math.random() * allPieces.length)];
                if (!options.includes(randomPiece)) {
                    options.push(randomPiece);
                }
            }
            
            return options.sort(() => Math.random() - 0.5);
        }

        function showQuestion() {
            if (currentQuestion >= quizQuestions.length) {
                showQuizResults();
                return;
            }
            
            const question = quizQuestions[currentQuestion];
            document.getElementById('quiz-question').innerHTML = `
                What is this piece? <br><br>
                <span style="font-size: 50px;">${question.piece}</span>
            `;
            
            const optionsContainer = document.getElementById('piece-options');
            optionsContainer.innerHTML = '';
            
            question.options.forEach(piece => {
                const option = document.createElement('div');
                option.className = 'piece-option';
                option.textContent = pieces[piece].name;
                option.onclick = () => checkAnswer(piece, question.piece);
                optionsContainer.appendChild(option);
            });
            
            document.getElementById('quiz-feedback').style.display = 'none';
            document.getElementById('next-question').style.display = 'none';
        }

        function checkAnswer(selected, correct) {
            const options = document.querySelectorAll('.piece-option');
            const feedback = document.getElementById('quiz-feedback');
            
            options.forEach(option => {
                option.onclick = null;
                if (option.textContent === pieces[correct].name) {
                    option.classList.add('correct');
                } else if (option.textContent === pieces[selected].name && selected !== correct) {
                    option.classList.add('wrong');
                }
            });
            
            if (selected === correct) {
                quizScore++;
                document.getElementById('quiz-score').textContent = quizScore;
                feedback.className = 'feedback correct';
                feedback.textContent = '🎉 Correct!';
            } else {
                feedback.className = 'feedback wrong';
                feedback.textContent = `❌ That was the ${pieces[correct].name}!`;
            }
            
            feedback.style.display = 'block';
            document.getElementById('next-question').style.display = 'block';
        }

        function nextQuestion() {
            currentQuestion++;
            showQuestion();
        }

        function showQuizResults() {
            const percentage = (quizScore / 5) * 100;
            let message = '';
            
            if (percentage >= 80) {
                message = '🏆 Excellent! Chess master!';
            } else if (percentage >= 60) {
                message = '⭐ Great job!';
            } else if (percentage >= 40) {
                message = '👍 Good try!';
            } else {
                message = '💪 Keep practicing!';
            }
            
            document.getElementById('quiz-question').innerHTML = `
                <h2>Quiz Complete!</h2>
                <p>Score: ${quizScore}/5</p>
                <p>${message}</p>
                <br>
                <button class="next-btn" onclick="startQuiz()">Play Again</button>
            `;
            
            document.getElementById('piece-options').innerHTML = '';
            document.getElementById('quiz-feedback').style.display = 'none';
            document.getElementById('next-question').style.display = 'none';
        }

        // Initialize
        createBoard('learn-board');
    </script>
</body>
</html>
