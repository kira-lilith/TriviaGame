# TriviaGame
var card = $("#quiz-area");
​
// Question set
var questions = [
  {
    question: "What is Lana Del Rey sun sign?",
    answers: ["Gemini", "Libra", "Cancer", "Leo"],
    correctAnswer: "Cancer"
  },
  {
    question: "What is her second lanuage?"
    answers: ["Spanish", "French", "Dutch", "Italian"],
    correctAnswer: "Spanish"
  },
  {
    question: " Who did she impersinte in the National Anthem MV?",
     "Marilyn Monroe", "Jackie O", "Elizabeth Taylor" Herself,"],
    correctAnswer: "Jackie O"
  },
  {
    question: "Got my ___ nail polish on. It's my favorite color and my favorite tone of song.'?",
    answers: ["Red", "Pink", "Yellow", "Blue"],
     correctAnswer: "Blue"
  },
  {
    question: "I was filled with ___, but blessed with beauty and rage.?",
    answers: ["Envy", "Hatred", "Poison", "None of the above"],
  },correctAnswer: "Poison"
  {
    question:
      "Which of the is not a Lana Del Rey Song?'",
    answers: [["THis Is What Makes Us Girls", "Carmen", "Mermaid", "Born To Die"],
  },correctAnswer: "Mermaid"
  {
    question: "Which one of her songs became the theme song for the movie The Great Gatsby?",
    answers: "Young and Beautiful”
  },
  {
    question: "Which song did she sign at Kim Kardashian and Kanye West wedding?",
    answers: ["Lust For Life", "Love", "Summertime Sadness", "Blue Jeans"],
    correctAnswer: "Summertime Sadness"
  }
];
​
// Variable that will hold the setInterval
var timer;
​
var game = {
  correct: 0,
  incorrect: 0,
  counter: 120,
​
  countdown: function() {
    game.counter--;
    $("#counter-number").html(game.counter);
    if (game.counter === 0) {
      console.log("TIME UP");
      game.done();
    }
  },
​
  start: function() {
    timer = setInterval(game.countdown, 1000);
​
    $("#sub-wrapper").prepend(
      "<h2>Time Remaining: <span id='counter-number'>120</span> Seconds</h2>"
    );
​
    $("#start").remove();
​
    for (var i = 0; i < questions.length; i++) {
      card.append("<h2>" + questions[i].question + "</h2>");
      for (var j = 0; j < questions[i].answers.length; j++) {
        card.append("<input type='radio' name='question-" + i +
          "' value='" + questions[i].answers[j] + "''>" + questions[i].answers[j]);
      }
    }
​
    card.append("<button id='done'>Done</button>");
  },
​
  done: function() {
    var inputs = card.children("input:checked");
    for (var i = 0; i < inputs.length; i++) {
      if ($(inputs[i]).val() === questions[i].correctAnswer) {
        game.correct++;
      } else {
        game.incorrect++;
      }
    }
    this.result();
  },
​
  result: function() {
    clearInterval(timer);
​
    $("#sub-wrapper h2").remove();
​
    card.html("<h2>All Done!</h2>");
    card.append("<h3>Correct Answers: " + this.correct + "</h3>");
    card.append("<h3>Incorrect Answers: " + this.incorrect + "</h3>");
  }
};
​
// CLICK EVENTS
​
$(document).on("click", "#start", function() {
  game.start();
});
​
$(document).on("click", "#done", function() {
  game.done();
});
