<script>
  let num1 = 0;
  let num2 = 0;
  let userAnswer = '';
  let correctAnswer = 0;
  let score = 0;
  let feedback = '';

  function generateQuestion() {
    num1 = Math.floor(Math.random() * 10) + 1;
    num2 = Math.floor(Math.random() * 10) + 1;
    correctAnswer = num1 + num2;
    userAnswer = '';
    feedback = '';
  }

  function checkAnswer() {
    if (parseInt(userAnswer) === correctAnswer) {
      score++;
      feedback = 'Correct!';
    } else {
      feedback = 'Incorrect. Try again!';
    }
    generateQuestion();
  }
</script>

<main>
  <h1 style="font-family: 'Helvetica Neue', sans-serif;">Math Quiz Game</h1>
  <p style="font-family: 'Helvetica Neue', sans-serif;">Your Score: {score}</p>

  <div>
    <p style="font-family: 'Helvetica Neue', sans-serif;">
      What is {num1} + {num2} ?
    </p>
    <input type="number" bind:value={userAnswer} style="padding: 8px; border-radius: 5px; border: 1px solid #ccc;" />
    <button on:click={checkAnswer} style="margin-top: 10px; padding: 8px 15px; border: none; background-color: #007aff; color: white; border-radius: 5px; cursor: pointer;">
      Submit
    </button>
    <p style="font-family: 'Helvetica Neue', sans-serif; margin-top: 10px; font-weight: bold;">{feedback}</p>
  </div>
</main>

<style>
  main {
    text-align: center;
    padding: 20px;
  }

  h1 {
    margin-bottom: 10px;
    color: #007aff;
    font-weight: bold;
    font-size: 24px;
  }

  p {
    margin-top: 10px;
    font-weight: bold;
    font-size: 16px;
  }
</style>

