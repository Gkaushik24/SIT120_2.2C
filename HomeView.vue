<template>
  <div class="quiz-container">
    <h1>{{ question }}</h1>
    <ul class="options">
      <li v-for="(option, index) in options" :key="index" @click="checkAnswer(index)">
        {{ option }}
      </li>
    </ul>
    <div v-if="showResult" class="result">
      <p>Correct: {{ correctAnswers }}</p>
      <p>Incorrect: {{ incorrectAnswers }}</p>
    </div>
  </div>
</template>

<script>
export default
{
  data()
  {
    return {
      questionIndex: 0,
      questions: [
        {
          question: "Who will win the Asia Cup?",
          options: ["India", "Pakistan", "Sri lanka"],
          correctAnswer: 0
        },
        {
          question: "Which will win the World Cup?",
          options: ["India", "Australia", "England"],
          correctAnswer: 1
        }
      ],
      correctAnswers: 0,
      incorrectAnswers: 0,
      showResult: false
    };
  },
  computed:
  {
    question()
    {
      return this.questions[this.questionIndex].question;
    },
    options()
    {
      return this.questions[this.questionIndex].options;
    }
  },
  methods:
  {
    checkAnswer(index)
    {
      if (index === this.questions[this.questionIndex].correctAnswer)
      {
        this.correctAnswers++;
      } else
      {
        this.incorrectAnswers++;
      }
      this.nextQuestion();
    },
    nextQuestion()
    {
      if (this.questionIndex < this.questions.length - 1)
      {
        this.questionIndex++;
      } else
      {
        this.showResult = true;
      }
    }
  }
};
</script>

<style scoped>
.quiz-container
{
  max-width: 600px;
  margin: 10px auto;
  text-align: center;
  padding: 30px;
}

.options
{
  list-style-type: none;
  padding: 20px;
  margin: 25px 0;
}

.options li
{
  background-color: #b5e81d;
  padding: 20px;
  margin: 8px;
  cursor: pointer;
}

.options li:hover
{
  background-color: #c9c719;
}

.result
{
  margin-top: 30px;
}
</style>

