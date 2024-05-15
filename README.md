<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Website Title</title>
    <style>
        /* Add your CSS styles here */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        header {
            background-color: #333;
            color: #fff;
            padding: 20px;
            text-align: center;
        }
        nav {
            background-color: #666;
            color: #fff;
            padding: 10px;
            text-align: center;
        }
        main {
            padding: 20px;
        }
        footer {
            background-color: #333;
            color: #fff;
            text-align: center;
            padding: 10px;
        }
        .quiz-question {
            margin-bottom: 20px;
        }
    </style>
</head>
<body>

<header>
    <h1>Welcome to Your Website</h1>
</header>

<nav>
    <a href="#">Home</a> |
    <a href="#">About</a> |
    <a href="#">Services</a> |
    <a href="#">Contact</a>
</nav>


    <h2>Quiz Section</h2>
    <form id="quiz-form">
        <div class="quiz-question">
            <p>Who is the creator of Black & White? </p>
            <label><input type="radio" name="q1" value="Jonathan Blow"> Jonathan Blow </label><br>
            <label><input type="radio" name="q1" value="Peter Molyneux"> Peter Molyneux </label><br>
            <label><input type="radio" name="q1" value="Alex Seropian"> Alex Seropian</label><br>
            <label><input type="radio" name="q1" value="Ken Kutaragi"> Ken Kutaragi</label><br>
        </div>

        <div class="quiz-question">
            <p>In what year has the Xbox 360 come out</p>
            <label><input type="radio" name="q2" value="2001"> 2001</label><br>
            <label><input type="radio" name="q2" value="2004"> 2004</label><br>
            <label><input type="radio" name="q2" vaalue="2005"> 2005</label><br>
            <label><input type="radio" name="q2" value="2006"> 2006</label><br>
        </div>

        <button type="button" onclick="submitQuiz()">Submit Quiz</button>
    </form>

    <div id="quiz-results"></div>
</main>

<footer>
    <p>&copy; 2024 Your Website</p>
</footer>

<script>
    function submitQuiz() {
        const form = document.getElementById('quiz-form');
        const formData = new FormData(form);
        let score = 0;

        for (const entry of formData.entries()) {
            const question = entry[0];
            const answer = entry[1];

            // Evaluate each question answer
            if (question === 'q1' && answer === "Peter Molyneux") {
                score++;
            }
            if (question === 'q2' && answer === "2005") {
                score++;
            }
        }

        const resultsContainer = document.getElementById('quiz-results');
        resultsContainer.innerHTML = `<p>You scored ${score} out of 2.</p>`;
    }
</script>

</body>
</html>
