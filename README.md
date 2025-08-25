# Smart-study
#Helps you to study smartly
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart Study Companion</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #4361ee;
            --secondary: #3a0ca3;
            --accent: #7209b7;
            --light: #f8f9fa;
            --dark: #212529;
            --success: #4cc9f0;
            --warning: #f72585;
            --gray: #6c757d;
            --light-gray: #e9ecef;
        }

        body {
            background-color: #f0f2f5;
            color: var(--dark);
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 30px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .logo h1 {
            font-size: 28px;
            font-weight: 700;
        }

        .logo-icon {
            font-size: 32px;
            background: white;
            color: var(--primary);
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 25px;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            padding: 8px 12px;
            border-radius: 6px;
            transition: background 0.3s;
        }

        nav a:hover, nav a.active {
            background: rgba(255, 255, 255, 0.2);
        }

        .main-content {
            display: grid;
            grid-template-columns: 1fr 3fr;
            gap: 25px;
        }

        .sidebar {
            background: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
        }

        .sidebar h2 {
            color: var(--primary);
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--light-gray);
        }

        .stats {
            margin-bottom: 30px;
        }

        .stat-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
        }

        .stat-item span:last-child {
            font-weight: 600;
            color: var(--primary);
        }

        .quick-actions button {
            display: block;
            width: 100%;
            padding: 12px;
            margin-bottom: 12px;
            border: none;
            border-radius: 8px;
            background: var(--light);
            color: var(--dark);
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s;
            text-align: left;
        }

        .quick-actions button:hover {
            background: var(--primary);
            color: white;
        }

        .quick-actions button i {
            margin-right: 10px;
        }

        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
        }

        .feature-card {
            background: white;
            border-radius: 10px;
            padding: 25px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-5px);
        }

        .feature-header {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }

        .feature-icon {
            width: 50px;
            height: 50px;
            border-radius: 12px;
            background: var(--light);
            color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            margin-right: 15px;
        }

        .feature-header h3 {
            color: var(--secondary);
        }

        .feature-content {
            margin-bottom: 20px;
        }

        .feature-content p {
            color: var(--gray);
            margin-bottom: 15px;
        }

        .feature-action {
            display: flex;
            justify-content: flex-end;
        }

        .btn {
            padding: 10px 20px;
            border: none;
            border-radius: 8px;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s;
        }

        .btn-primary {
            background: var(--primary);
            color: white;
        }

        .btn-primary:hover {
            background: var(--secondary);
        }

        .flashcard {
            background: var(--light);
            border-radius: 10px;
            padding: 20px;
            margin: 15px 0;
            position: relative;
        }

        .flashcard-content {
            min-height: 100px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            font-size: 18px;
            padding: 20px;
        }

        .flashcard-actions {
            display: flex;
            justify-content: space-between;
            margin-top: 15px;
        }

        .timer-display {
            font-size: 42px;
            font-weight: 700;
            text-align: center;
            color: var(--primary);
            margin: 20px 0;
        }

        .timer-controls {
            display: flex;
            justify-content: center;
            gap: 15px;
        }

        .timer-btn {
            padding: 10px 25px;
            border: none;
            border-radius: 8px;
            font-weight: 500;
            cursor: pointer;
        }

        .timer-start {
            background: var(--success);
            color: white;
        }

        .timer-pause {
            background: var(--warning);
            color: white;
        }

        .timer-reset {
            background: var(--gray);
            color: white;
        }

        .notes-list {
            margin-top: 20px;
        }

        .note-item {
            padding: 15px;
            border-left: 4px solid var(--primary);
            background: var(--light);
            margin-bottom: 15px;
            border-radius: 4px;
        }

        .note-title {
            font-weight: 600;
            margin-bottom: 8px;
        }

        .note-meta {
            display: flex;
            justify-content: space-between;
            color: var(--gray);
            font-size: 14px;
        }

        footer {
            text-align: center;
            margin-top: 50px;
            padding: 20px;
            color: var(--gray);
            font-size: 14px;
        }

        @media (max-width: 768px) {
            .main-content {
                grid-template-columns: 1fr;
            }
            
            .header-content {
                flex-direction: column;
                text-align: center;
                gap: 20px;
            }
            
            nav ul {
                justify-content: center;
                flex-wrap: wrap;
            }
            
            .features {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="header-content">
                <div class="logo">
                    <div class="logo-icon">
                        <i class="fas fa-graduation-cap"></i>
                    </div>
                    <h1>Smart Study Companion</h1>
                </div>
                <nav>
                    <ul>
                        <li><a href="#" class="active">Dashboard</a></li>
                        <li><a href="#">Flashcards</a></li>
                        <li><a href="#">Timetable</a></li>
                        <li><a href="#">Focus Mode</a></li>
                        <li><a href="#">Notes</a></li>
                    </ul>
                </nav>
            </div>
        </header>

        <div class="main-content">
            <aside class="sidebar">
                <div class="stats">
                    <h2>Study Stats</h2>
                    <div class="stat-item">
                        <span>Today's Study Time:</span>
                        <span>2h 15m</span>
                    </div>
                    <div class="stat-item">
                        <span>Flashcards Created:</span>
                        <span>42</span>
                    </div>
                    <div class="stat-item">
                        <span>Tasks Completed:</span>
                        <span>7/10</span>
                    </div>
                    <div class="stat-item">
                        <span>Current Streak:</span>
                        <span>5 days</span>
                    </div>
                </div>

                <div class="quick-actions">
                    <h2>Quick Actions</h2>
                    <button><i class="fas fa-plus"></i> Create Flashcard</button>
                    <button><i class="fas fa-book"></i> Add Note</button>
                    <button><i class="fas fa-clock"></i> Start Focus Timer</button>
                    <button><i class="fas fa-share-alt"></i> Share Notes</button>
                </div>
            </aside>

            <main class="features">
                <div class="feature-card">
                    <div class="feature-header">
                        <div class="feature-icon">
                            <i class="fas fa-layer-group"></i>
                        </div>
                        <h3>AI Flashcard Generator</h3>
                    </div>
                    <div class="feature-content">
                        <p>Automatically generate flashcards from your notes or uploaded documents.</p>
                        <div class="flashcard">
                            <div class="flashcard-content">
                                <p>What is the capital of France?</p>
                            </div>
                            <div class="flashcard-actions">
                                <button class="btn btn-primary">Show Answer</button>
                                <div>
                                    <i class="fas fa-edit"></i>
                                    <i class="fas fa-share-alt"></i>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="feature-action">
                        <button class="btn btn-primary">Generate Flashcards</button>
                    </div>
                </div>

                <div class="feature-card">
                    <div class="feature-header">
                        <div class="feature-icon">
                            <i class="fas fa-table"></i>
                        </div>
                        <h3>Study Timetable</h3>
                    </div>
                    <div class="feature-content">
                        <p>Plan your study sessions and track your progress.</p>
                        <div class="stat-item">
                            <span>Mon - Math:</span>
                            <span>9:00 - 10:30</span>
                        </div>
                        <div class="stat-item">
                            <span>Tue - Science:</span>
                            <span>14:00 - 15:30</span>
                        </div>
                        <div class="stat-item">
                            <span>Wed - History:</span>
                            <span>10:00 - 11:30</span>
                        </div>
                        <div class="stat-item">
                            <span>Thu - Language:</span>
                            <span>13:00 - 14:30</span>
                        </div>
                    </div>
                    <div class="feature-action">
                        <button class="btn btn-primary">View Full Timetable</button>
                    </div>
                </div>

                <div class="feature-card">
                    <div class="feature-header">
                        <div class="feature-icon">
                            <i class="fas fa-clock"></i>
                        </div>
                        <h3>Focus Timer</h3>
                    </div>
                    <div class="feature-content">
                        <p>Use the Pomodoro technique to enhance your focus and productivity.</p>
                        <div class="timer-display">
                            25:00
                        </div>
                        <div class="timer-controls">
                            <button class="timer-btn timer-start">Start</button>
                            <button class="timer-btn timer-pause">Pause</button>
                            <button class="timer-btn timer-reset">Reset</button>
                        </div>
                    </div>
                    <div class="feature-action">
                        <button class="btn btn-primary">Customize Timer</button>
                    </div>
                </div>

                <div class="feature-card">
                    <div class="feature-header">
                        <div class="feature-icon">
                            <i class="fas fa-sticky-note"></i>
                        </div>
                        <h3>Collaborative Notes</h3>
                    </div>
                    <div class="feature-content">
                        <p>Create, share and collaborate on notes with your classmates.</p>
                        <div class="notes-list">
                            <div class="note-item">
                                <div class="note-title">Biology - Cell Structure</div>
                                <div class="note-meta">
                                    <span>Last modified: 2 hours ago</span>
                                    <span>Shared with 3 classmates</span>
                                </div>
                            </div>
                            <div class="note-item">
                                <div class="note-title">History - World War II</div>
                                <div class="note-meta">
                                    <span>Last modified: 1 day ago</span>
                                    <span>Private</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="feature-action">
                        <button class="btn btn-primary">Create New Note</button>
                    </div>
                </div>
            </main>
        </div>

        <footer>
            <p>Smart Study Companion © 2023 | AI-Powered Learning Assistant</p>
        </footer>
    </div>

    <script>
        // Timer functionality
        const timerDisplay = document.querySelector('.timer-display');
        const startBtn = document.querySelector('.timer-start');
        const pauseBtn = document.querySelector('.timer-pause');
        const resetBtn = document.querySelector('.timer-reset');
        
        let timer;
        let minutes = 25;
        let seconds = 0;
        let isRunning = false;
        
        function updateDisplay() {
            timerDisplay.textContent = `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
        }
        
        function startTimer() {
            if (!isRunning) {
                isRunning = true;
                timer = setInterval(() => {
                    if (seconds === 0) {
                        if (minutes === 0) {
                            clearInterval(timer);
                            isRunning = false;
                            alert('Focus session completed! Take a break.');
                            return;
                        }
                        minutes--;
                        seconds = 59;
                    } else {
                        seconds--;
                    }
                    updateDisplay();
                }, 1000);
            }
        }
        
        function pauseTimer() {
            clearInterval(timer);
            isRunning = false;
        }
        
        function resetTimer() {
            clearInterval(timer);
            isRunning = false;
            minutes = 25;
            seconds = 0;
            updateDisplay();
        }
        
        startBtn.addEventListener('click', startTimer);
        pauseBtn.addEventListener('click', pauseTimer);
        resetBtn.addEventListener('click', resetTimer);
        
        // Flashcard functionality
        const flashcard = document.querySelector('.flashcard');
        const flashcardContent = document.querySelector('.flashcard-content p');
        const showAnswerBtn = document.querySelector('.flashcard-actions .btn');
        
        const flashcards = [
            { question: 'What is the capital of France?', answer: 'Paris' },
            { question: 'What is the largest planet in our solar system?', answer: 'Jupiter' },
            { question: 'Who painted the Mona Lisa?', answer: 'Leonardo da Vinci' }
        ];
        
        let currentCard = 0;
        let showingAnswer = false;
        
        showAnswerBtn.addEventListener('click', () => {
            if (showingAnswer) {
                flashcardContent.textContent = flashcards[currentCard].question;
                showAnswerBtn.textContent = 'Show Answer';
            } else {
                flashcardContent.textContent = flashcards[currentCard].answer;
                showAnswerBtn.textContent = 'Show Question';
            }
            showingAnswer = !showingAnswer;
        });
        
        // Simulate generating new flashcards
        const generateBtn = document.querySelector('.feature-card:first-child .feature-action .btn');
        generateBtn.addEventListener('click', () => {
            currentCard = (currentCard + 1) % flashcards.length;
            showingAnswer = false;
            flashcardContent.textContent = flashcards[currentCard].question;
            showAnswerBtn.textContent = 'Show Answer';
            alert('New flashcards generated from your notes!');
        });
        
        // Initialize display
        updateDisplay();
    </script>
</body>
</html>
