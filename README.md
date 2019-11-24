<!DOCTYPE html>
<html>
<head>
  <title>Lana Del Rey Trivia Game</title>
  <link rel="stylesheet" href="assets/reset.css">
  <link rel="stylesheet" href="assets/style.css">
</head>
<body>
  <div class="container">
    <header class="title">
      <img src="https://images.alphacoders.com/576/thumb-1920-576947.jpg" alt="Lana Del Rey image">
      <h1>Lana Del Rey Trivia Game</h1>
      <h3>Time Remaining: <span id="countdown">30</span></h3>
    </header>
    <!-- Dynamically created quiz questions section -->
    <main id="quiz__questions" class="block">
      <form id="form"></form>
      <button type="submit" form="form" id="quiz__questions--btn">Check Answers</button>
    </main>
    <!-- Quiz results section -->
    <div id="quiz__results" class="block">
      <ul>
        <li>Correct Answers: <span id="correct">0</span></li>
        <li>Incorrect Answers: <span id="incorrect">0</span></li>
        <li>Unanswered: <span id="unanswered">0</span></li>
      </ul>
    </div>
  </div>
<script src="assets/game.js"></script>
</body>
</html>
