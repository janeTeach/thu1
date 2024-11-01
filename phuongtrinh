<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <title>Bài Trắc Nghiệm</title>
    <style>
        .question {
            margin-bottom: 20px;
        }
        .correct {
            color: green;
        }
        .incorrect {
            color: red;
        }
        img {
            max-width: 200px;
        }
    </style>
    <script type="text/javascript" async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML"></script>
</head>
<body>
    <h1>Bài Trắc Nghiệm</h1>
    <form id="quizForm">
        <div class="question" id="question1">
            <p>1. Đâu là thủ đô của Việt Nam?</p>
            <img src="https://i.postimg.cc/SNhtxDHS/Untitled-01.png" alt="Hình minh họa" height="86" width="56">
        </div>
        <div class="question" id="question2">
            <p>2. Giải phương trình $$\sqrt{a^2 + b^2} = c$$</p>
        </div>
        <button type="button" onclick="checkAnswers()">Nộp Bài</button>
    </form>
    <p id="result"></p>

    <script>
        const questions = [
            {
                question: "Đâu là thủ đô của Việt Nam?",
                answers: ["TP. Hồ Chí Minh", "Hà Nội", "Đà Nẵng", "Cần Thơ"],
                correct: "Hà Nội",
            },
            {
                question: "Giải phương trình $$\\sqrt{a^2 + b^2} = c$$",
                answers: ["$$\\sqrt{3^2 + 4^2} = 5$$", "$$\\sqrt{2^2 + 2^2} = 3$$", "$$\\sqrt{1^2 + 1^2} = 2$$", "$$\\sqrt{0^2 + 0^2} = 0$$"],
                correct: "$$\\sqrt{3^2 + 4^2} = 5$$"
            }
        ];

        function shuffleArray(array) {
            for (let i = array.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [array[i], array[j]] = [array[j], array[i]];
            }
        }

        function loadQuestions() {
            questions.forEach((q, index) => {
                shuffleArray(q.answers);
                const questionDiv = document.getElementById(`question${index + 1}`);
                q.answers.forEach(answer => {
                    const radioBtn = document.createElement('input');
                    radioBtn.type = 'radio';
                    radioBtn.name = `q${index + 1}`;
                    radioBtn.value = answer;
                    questionDiv.appendChild(radioBtn);
                    questionDiv.appendChild(document.createTextNode(answer));
                    questionDiv.appendChild(document.createElement('br'));
                });
                if (q.image) {
                    const img = document.createElement('img');
                    img.src = q.image;
                    questionDiv.appendChild(img);
                }
            });
        }

        function checkAnswers() {
            questions.forEach((q, index) => {
                const selectedAnswer = document.querySelector(`input[name="q${index + 1}"]:checked`);
                const questionDiv = document.getElementById(`question${index + 1}`);
                if (selectedAnswer) {
                    if (selectedAnswer.value === q.correct) {
                        selectedAnswer.parentNode.insertAdjacentHTML('beforeend', '<span class="correct"> - Đúng</span>');
                    } else {
                        selectedAnswer.parentNode.insertAdjacentHTML('beforeend', '<span class="incorrect"> - Sai</span>');
                    }
                }
            });

            let correctAnswers = 0;
            questions.forEach((q, index) => {
                const selectedAnswer = document.querySelector(`input[name="q${index + 1}"]:checked`);
                if (selectedAnswer && selectedAnswer.value === q.correct) {
                    correctAnswers++;
                }
            });
            document.getElementById('result').innerHTML = `Bạn trả lời đúng ${correctAnswers} trên ${questions.length} câu hỏi.`;
            MathJax.typeset();
        }

        window.onload = loadQuestions;
    </script>
</body>
</html>
