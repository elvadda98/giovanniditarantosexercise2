<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ESL Vocabulary Exercise</title>
    <style>
        :root {
            --teal: #2dd4bf;
            --teal-dark: #14b8a6;
            --green: #86efac;
            --green-dark: #4ade80;
            --gray: #f3f4f6;
            --gray-dark: #e5e7eb;
            --font: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            font-family: var(--font);
            background-color: #f9fafb;
            color: #1f2937;
            line-height: 1.6;
            padding: 20px;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            border-radius: 12px;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
            padding: 24px;
        }

        h1 {
            color: var(--teal-dark);
            text-align: center;
            margin-bottom: 24px;
        }

        .nav-buttons {
            display: flex;
            justify-content: center;
            gap: 12px;
            margin-bottom: 24px;
            flex-wrap: wrap;
        }

        button {
            background: linear-gradient(135deg, var(--teal), var(--teal-dark));
            color: white;
            border: none;
            padding: 10px 16px;
            border-radius: 6px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.2s;
        }

        button:hover {
            background: linear-gradient(135deg, var(--teal-dark), #0d9488);
        }

        .section {
            display: none;
        }

        .section.active {
            display: block;
        }

        .vocab-item {
            background: white;
            border: 1px solid var(--gray-dark);
            border-radius: 8px;
            padding: 16px;
            margin-bottom: 16px;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
        }

        .vocab-word {
            font-weight: bold;
            color: var(--teal-dark);
            font-size: 1.2em;
            margin-bottom: 4px;
        }

        .vocab-context {
            color: #6b7280;
            font-style: italic;
            margin-bottom: 8px;
        }

        .vocab-meaning {
            margin-bottom: 8px;
        }

        .vocab-example {
            background: var(--gray);
            padding: 12px;
            border-radius: 6px;
            margin-top: 8px;
            font-style: italic;
        }

        .word-bank {
            background: linear-gradient(135deg, var(--green), var(--green-dark));
            color: white;
            padding: 12px;
            border-radius: 6px;
            margin-bottom: 16px;
            font-weight: 600;
            text-align: center;
        }

        .fill-gap {
            margin-bottom: 16px;
            padding: 12px;
            background: white;
            border-radius: 6px;
            border: 1px solid var(--gray-dark);
        }

        .fill-gap input {
            padding: 8px;
            border: 1px solid var(--gray-dark);
            border-radius: 4px;
            width: 120px;
            text-align: center;
        }

        .match-container {
            display: flex;
            justify-content: space-between;
            gap: 24px;
        }

        .match-column {
            flex: 1;
        }

        .match-item {
            background: white;
            border: 1px solid var(--gray-dark);
            border-radius: 6px;
            padding: 12px;
            margin-bottom: 8px;
            cursor: pointer;
            transition: all 0.2s;
        }

        .match-item:hover {
            background: var(--gray);
        }

        .match-item.selected {
            background: var(--teal);
            color: white;
        }

        .match-item.correct {
            background: var(--green-dark);
            color: white;
        }

        .score {
            position: fixed;
            top: 20px;
            right: 20px;
            background: white;
            padding: 12px 16px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            font-weight: 600;
            color: var(--teal-dark);
        }

        .feedback {
            margin-top: 8px;
            font-size: 0.9em;
            color: #6b7280;
        }

        .correct {
            color: var(--green-dark);
            font-weight: bold;
        }

        .incorrect {
            color: #ef4444;
            font-weight: bold;
        }

        .pronunciation-item {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 16px;
            padding: 12px;
            background: white;
            border-radius: 6px;
            border: 1px solid var(--gray-dark);
        }

        .pronunciation-blank {
            background: var(--gray);
            padding: 8px 12px;
            border-radius: 4px;
            min-width: 120px;
            text-align: center;
            font-weight: 600;
            color: #6b7280;
        }

        .microphone-btn {
            background: var(--teal);
            color: white;
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            cursor: pointer;
            font-size: 1.1em;
        }

        .microphone-btn:disabled {
            background: var(--gray-dark);
            cursor: not-allowed;
        }

        @media (max-width: 768px) {
            .match-container {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <div class="score">Score: 0 / 12</div>
    <div class="container">
        <h1>ESL Vocabulary Exercise</h1>

        <div class="nav-buttons">
            <button onclick="showSection('vocab-list')">Vocabulary List</button>
            <button onclick="showSection('fill-gaps-writing')">Fill in the Gaps (Writing)</button>
            <button onclick="showSection('match-definitions')">Match Definitions</button>
            <button onclick="showSection('fill-gaps-pronunciation')">Fill in the Gaps (Pronunciation)</button>
        </div>

        <div id="vocab-list" class="section active">
            <h2>Vocabulary List</h2>
            <div class="vocab-item">
                <div class="vocab-word">subsequently <button onclick="speak('subsequently')" class="microphone-btn">▶️</button></div>
                <div class="vocab-context">(as successivamente, dopo)</div>
                <div class="vocab-meaning">After something else; later.</div>
                <div class="vocab-example">He first studied law and subsequently became a lawyer.</div>
            </div>
            <div class="vocab-item">
                <div class="vocab-word">apologize <button onclick="speak('apologize')" class="microphone-btn">▶️</button></div>
                <div class="vocab-context">(as scusarsi)</div>
                <div class="vocab-meaning">To express regret for something you have done wrong.</div>
                <div class="vocab-example">She decided to apologize for her mistake.</div>
            </div>
            <div class="vocab-item">
                <div class="vocab-word">delay <button onclick="speak('delay')" class="microphone-btn">▶️</button></div>
                <div class="vocab-context">(as ritardo, posticipare)</div>
                <div class="vocab-meaning">A situation in which something happens later than it should.</div>
                <div class="vocab-example">There was a delay in the train schedule due to bad weather.</div>
            </div>
            <div class="vocab-item">
                <div class="vocab-word">light <button onclick="speak('light')" class="microphone-btn">▶️</button></div>
                <div class="vocab-context">(as leggero)</div>
                <div class="vocab-meaning">Not heavy; weighing very little.</div>
                <div class="vocab-example">This bag is very light, you can carry it easily.</div>
            </div>
        </div>

        <div id="fill-gaps-writing" class="section">
            <h2>Fill in the Gaps (Writing)</h2>
            <div class="word-bank">Word Bank: subsequently, apologize, delay, light</div>
            <div class="fill-gap">
                <span>I need to ___ for being late to the meeting.</span>
                <input type="text" id="gap1" data-answer="apologize">
                <div id="feedback1" class="feedback"></div>
            </div>
            <div class="fill-gap">
                <span>The flight was cancelled due to a long ___.</span>
                <input type="text" id="gap2" data-answer="delay">
                <div id="feedback2" class="feedback"></div>
            </div>
            <div class="fill-gap">
                <span>He first worked as a teacher and ___ became a principal.</span>
                <input type="text" id="gap3" data-answer="subsequently">
                <div id="feedback3" class="feedback"></div>
            </div>
            <div class="fill-gap">
                <span>This suitcase is so ___ that I can lift it with one hand.</span>
                <input type="text" id="gap4" data-answer="light">
                <div id="feedback4" class="feedback"></div>
            </div>
            <div style="display: flex; gap: 12px; margin-top: 20px;">
                <button onclick="checkWritingAnswers()">Check Answers</button>
                <button onclick="resetWritingAnswers()">Reset</button>
            </div>
        </div>

        <div id="match-definitions" class="section">
            <h2>Match Definitions</h2>
            <div class="match-container">
                <div class="match-column">
                    <h3>Words</h3>
                    <div class="match-item" onclick="selectWord(this)" data-word="subsequently">subsequently</div>
                    <div class="match-item" onclick="selectWord(this)" data-word="apologize">apologize</div>
                    <div class="match-item" onclick="selectWord(this)" data-word="delay">delay</div>
                    <div class="match-item" onclick="selectWord(this)" data-word="light">light</div>
                </div>
                <div class="match-column">
                    <h3>Definitions</h3>
                    <div class="match-item" onclick="selectDefinition(this)" data-definition="Not heavy; weighing very little.">Not heavy; weighing very little.</div>
                    <div class="match-item" onclick="selectDefinition(this)" data-definition="A situation in which something happens later than it should.">A situation in which something happens later than it should.</div>
                    <div class="match-item" onclick="selectDefinition(this)" data-definition="After something else; later.">After something else; later.</div>
                    <div class="match-item" onclick="selectDefinition(this)" data-definition="To express regret for something you have done wrong.">To express regret for something you have done wrong.</div>
                </div>
            </div>
            <div style="margin-top: 20px;">
                <button onclick="resetMatching()">Reset</button>
            </div>
        </div>

        <div id="fill-gaps-pronunciation" class="section">
            <h2>Fill in the Gaps (Pronunciation)</h2>
            <div class="word-bank">Word Bank: subsequently, apologize, delay, light</div>
            <div class="pronunciation-item">
                <span>He first worked as a teacher and ___ became a principal.</span>
                <div class="pronunciation-blank" id="pronunciation1" data-answer="subsequently">___</div>
                <button class="microphone-btn" onclick="startRecognition(1, 'subsequently')">🎤</button>
                <div id="pronunciation-feedback1" class="feedback"></div>
            </div>
            <div class="pronunciation-item">
                <span>I need to ___ for being late to the meeting.</span>
                <div class="pronunciation-blank" id="pronunciation2" data-answer="apologize">___</div>
                <button class="microphone-btn" onclick="startRecognition(2, 'apologize')">🎤</button>
                <div id="pronunciation-feedback2" class="feedback"></div>
            </div>
            <div class="pronunciation-item">
                <span>The flight was cancelled due to a long ___.</span>
                <div class="pronunciation-blank" id="pronunciation3" data-answer="delay">___</div>
                <button class="microphone-btn" onclick="startRecognition(3, 'delay')">🎤</button>
                <div id="pronunciation-feedback3" class="feedback"></div>
            </div>
            <div class="pronunciation-item">
                <span>This suitcase is so ___ that I can lift it with one hand.</span>
                <div class="pronunciation-blank" id="pronunciation4" data-answer="light">___</div>
                <button class="microphone-btn" onclick="startRecognition(4, 'light')">🎤</button>
                <div id="pronunciation-feedback4" class="feedback"></div>
            </div>
        </div>
    </div>

    <script>
        let score = 0;
        const totalScore = 12;
        let selectedWord = null;
        let selectedDefinition = null;
        let recognition = null;

        function updateScore() {
            document.querySelector('.score').textContent = `Score: ${score} / ${totalScore}`;
        }

        function showSection(sectionId) {
            document.querySelectorAll('.section').forEach(section => {
                section.classList.remove('active');
            });
            document.getElementById(sectionId).classList.add('active');
        }

        function speak(word) {
            const u = new SpeechSynthesisUtterance(word);
            u.lang = "en-US";
            speechSynthesis.speak(u);
        }

        // Writing Fill in the Gaps
        function checkWritingAnswers() {
            let localScore = 0;
            for (let i = 1; i <= 4; i++) {
                const input = document.getElementById(`gap${i}`);
                const answer = input.dataset.answer;
                const feedback = document.getElementById(`feedback${i}`);
                if (input.value.toLowerCase().trim() === answer.toLowerCase()) {
                    input.style.backgroundColor = '#dcfce7';
                    feedback.textContent = 'Correct!';
                    feedback.className = 'feedback correct';
                    localScore++;
                } else {
                    input.style.backgroundColor = '#fee2e2';
                    feedback.textContent = `Incorrect. The correct answer is "${answer}".`;
                    feedback.className = 'feedback incorrect';
                }
            }
            score += localScore;
            updateScore();
        }

        function resetWritingAnswers() {
            for (let i = 1; i <= 4; i++) {
                const input = document.getElementById(`gap${i}`);
                const feedback = document.getElementById(`feedback${i}`);
                input.value = '';
                input.style.backgroundColor = '';
                feedback.textContent = '';
            }
        }

        // Match Definitions
        function selectWord(element) {
            if (element.classList.contains('correct')) return;
            if (selectedWord) selectedWord.classList.remove('selected');
            selectedWord = element;
            element.classList.add('selected');
            checkMatch();
        }

        function selectDefinition(element) {
            if (element.classList.contains('correct')) return;
            if (selectedDefinition) selectedDefinition.classList.remove('selected');
            selectedDefinition = element;
            element.classList.add('selected');
            checkMatch();
        }

        function checkMatch() {
            if (!selectedWord || !selectedDefinition) return;
            const word = selectedWord.dataset.word;
            const definition = selectedDefinition.dataset.definition;
            const correctDefinition = {
                'subsequently': 'After something else; later.',
                'apologize': 'To express regret for something you have done wrong.',
                'delay': 'A situation in which something happens later than it should.',
                'light': 'Not heavy; weighing very little.'
            };
            if (correctDefinition[word] === definition) {
                selectedWord.classList.add('correct');
                selectedDefinition.classList.add('correct');
                score++;
                updateScore();
            }
            selectedWord = null;
            selectedDefinition = null;
        }

        function resetMatching() {
            document.querySelectorAll('.match-item').forEach(item => {
                item.classList.remove('selected', 'correct');
            });
        }

        // Pronunciation Fill in the Gaps
        function startRecognition(id, expectedWord) {
            const feedbackElement = document.getElementById(`pronunciation-feedback${id}`);
            const blankElement = document.getElementById(`pronunciation${id}`);
            const button = event.target;

            if (!('webkitSpeechRecognition' in window) && !('SpeechRecognition' in window)) {
                feedbackElement.textContent = 'Speech recognition not supported in your browser.';
                feedbackElement.className = 'feedback incorrect';
                return;
            }

            button.disabled = true;
            feedbackElement.textContent = 'Listening...';

            const recognition = new (window.SpeechRecognition || window.webkitSpeechRecognition)();
            recognition.lang = 'en-US';
            recognition.interimResults = false;
            recognition.maxAlternatives = 1;

            recognition.onresult = function(event) {
                const spokenWord = event.results[0][0].transcript.trim().toLowerCase();
                const normalizedExpected = expectedWord.toLowerCase();
                const normalizedSpoken = spokenWord.toLowerCase();

                if (normalizedSpoken === normalizedExpected) {
                    blankElement.textContent = expectedWord;
                    blankElement.style.backgroundColor = '#dcfce7';
                    feedbackElement.textContent = 'Correct!';
                    feedbackElement.className = 'feedback correct';
                    score++;
                    updateScore();
                } else {
                    feedbackElement.textContent = `Incorrect. Try again!`;
                    feedbackElement.className = 'feedback incorrect';
                }
                button.disabled = false;
            };

            recognition.onerror = function(event) {
                feedbackElement.textContent = 'Error occurred in recognition.';
                feedbackElement.className = 'feedback incorrect';
                button.disabled = false;
            };

            recognition.start();
        }
    </script>
</body>
</html>
