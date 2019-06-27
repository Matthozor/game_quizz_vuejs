<template>
  <div id="app">
    <titlepage msg="Game-Quizz"/>

    <div class="container">

      <question :question="currentQuestion.label" :choices="currentQuestion.choices"
      :correct="currentQuestion.correct" :imgJeux="currentQuestion.imgJeux" />
    </div>
    <button class="buttonQuizz" @click="currentQuestionIndex++">Next</button>
    <br>
    <buttonScore />
    <footerScoring :points="points" />
  </div>
</template>

<script>
import titlepage from './components/title.vue'
import question from './components/question.vue'
import footerScoring from './components/footerScoring.vue'
import buttonScore from './components/buttonScore.vue'
import 'reset-css';



export default {
  name: 'app',
  components: {
    titlepage,
    question,
    footerScoring,
    buttonScore
  },
  computed: {
    currentQuestion() {
      return this.questions[this.currentQuestionIndex];
    }
  },
  data() {
    return {
      points: 0,
      currentQuestionIndex: 0,
      questions: [
        {
          label: 'Comment s\'appelle le fruit dans Crash Bandicoot ?',
          choices: [
            'Mango',
            'Wumpa',
            'Danou',
            'Pomme'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/crash-bandicoot.jpg')
        },

        {
          label: 'Combien World of Warcraft contient d\'éxtension(s) ?',
          choices: [
            '9',
            '5',
            '7',
            '3'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/wow.png')
        },

         {
          label: 'Dans minecraft combien de temp dure le jour et la nuit ?',
          choices: [
            '10 minutes',
            '6 minutes',
            '8 minutes',
            'Cela dépend de la fatigue du personnage'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/minecraft.jpg')
        },

         {
          label: 'Comment s\'appelle l\'armure légendaire de Assassin\'s creed origin ?',
          choices: [
            'L\'armure d\'inu',
            'L\'armure d\'izu',
            'L\'armure d\'imu',
            'L\'armure d\'isu'
          ],
          correct: 'answer 2',
          imgJeux: require('../src/assets/img/assassin.jpg')
        },

         {
          label: 'Combien y-a t\'il de dragon à liberer en tout dans Spyro 1 ?',
          choices: [
            '120',
            '80',
            '101',
            '76'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/spyro.jpg')
        },

         {
          label: 'Dans Diablo 3, pour accéder au monde des vaches il faut créer le "Baton de bouvier" lequel de ces ingrédients est faux ?',
          choices: [
            'Cloche de wirt',
            'Arc-en-ciel liquide',
            'Tibia de léoric',
            'Gemme bouillonnante'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/diablo.jpg')
        },
           {
          label: 'Dans Binding of Isaac, l\'objet "Cricket\'s Head" améliore les dégats :',
          choices: [
            '+ 0,5 puis x 1,5 le tout',
            '+ 1 puis x 1,25 le tout',
            '+ 1,5 puis x 2 le tout',
            '+ 0,75 puis x 1,75 le tout'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/binding.jpg')
        },
           {
          label: 'Dans GTA-San Andreas, le code pour les armes palier 3 était :',
          choices: [
            'L1 L2 R1 L2 GAUCHE BAS DROITE HAUT GAUCHE HAUT HAUT HAUT',
            'L1 R1 L2 R2 GAUCHE BAS DROITE TRIANGLE TRINAGLE CARRÉ CARRÉ ROND',
            'R1 R2 L1 R2 GAUCHE BAS DROITE HAUT GAUCHE BAS BAS BAS',
            'R1 R2 L1 L2 GAUCHE BAS HAUT DROITE HAUT BAS BAS BAS'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/gta.jpg')
        },
           {
          label: 'Les sims avaient pour langage le "Simlish", quelle proposition n\'est pas en Simlish ?',
          choices: [
            'answer1',
            'answer2',
            'answer3',
            'answer4'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/sims.png')
        },
           {
          label: 'Question 10',
          choices: [
            'answer1',
            'answer2',
            'answer3',
            'answer4'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/mariokart.jpg')
        },
           {
          label: 'Question 11',
          choices: [
            'answer1',
            'answer2',
            'answer3',
            'answer4'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/dofus.jpeg')
        },
        {
          label: 'Question 12',
          choices: [
            'answer1',
            'answer2',
            'answer3',
            'answer4'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/rayman.jpg')
        },

        {
          label: 'Question 13',
          choices: [
            'answer1',
            'answer2',
            'answer3',
            'answer4'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/bubble.jpeg')
        },

         {
          label: 'Question 14',
          choices: [
            'answer1',
            'answer2',
            'answer3',
            'answer4'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/geralt.jpg')
        },

         {
          label: 'Question 15',
          choices: [
            'answer1',
            'answer2',
            'answer3',
            'answer4'
          ],
          correct: 'answer 2',
          imgJeux: require('../src/assets/img/resident.jpg')
        },

         {
          label: 'Question 16',
          choices: [
            'answer1',
            'answer2',
            'answer3',
            'answer4'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/ssx.jpg')
        },

         {
          label: 'Question 17',
          choices: [
            'answer1',
            'answer2',
            'answer3',
            'answer4'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/pokemon.png')
        },
           {
          label: 'Question 18',
          choices: [
            'answer1',
            'answer2',
            'answer3',
            'answer4'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/cuphead.jpg')
        },
           {
          label: 'Question 19',
          choices: [
            'answer1',
            'answer2',
            'answer3',
            'answer4'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/heartOf.jpg')
        },
           {
          label: 'Question 20',
          choices: [
            'answer1',
            'answer2',
            'answer3',
            'answer4'
          ],
          correct: 'answer2',
          imgJeux: require('../src/assets/img/tetris.png')
        }
      ]
    }
  }
}
</script>

<style>

html {
  height: 100%;
  width: 100%;
}
* {
    box-sizing: border-box;
  }
body {
  background-color: #2c3e50;
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #3c546d;;
  margin-top: 60px;
  margin: 0;
  /* color: #FFF; */
  font-weight: bold;
  width: 100%;
  height: 100%;
  
}
.title-border {
  border-bottom: 3px solid #ffffffd4;
  border-radius: 0px 0px 10px 10px;
  top: 0;
  background-color: #ffffff8a;
}
h1 {
  color: #FFF;
    margin: 0;
    height: 80px;
    display: flex;
    align-items: center;
    justify-content: center;
}
.container {
  background-color: #ffffffbd;
  border-bottom: 2px solid #FFF;
  border-top: 2px solid #FFF;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  margin: 0 auto;
  width: 50%;
  margin-bottom: 25px;
  margin-top: 25px;
}
.container p {
  background-color: #577c9c9c;
  /* color: rgba(0, 0, 0, 0.57); */
  color: #FFF;
  width: 100%;
}
.container input {
  cursor: pointer;
  margin: 0 auto;
  width: 20px;
  height: 20px;
}
.container span {
  margin-bottom: 10px;
}
.container-choice {
  display: flex;
  flex-direction: column;
}
a {
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #ffffffd4;
    color: #2c3e50;
    font-size: 15px;
    width: 90px;
    height: 70px;
    border-radius: 10px;
    margin: 0 auto;
}

.buttonQuizz{
  cursor: pointer;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  font-weight: bold;
  background-color: #ffffffd4;
  color: #2c3e50;
  font-size: 15px;
  width: 90px;
  height: 70px;
  border-radius: 10px;
}
.buttonQuizz:hover {
  background-color: #577c9c9c;
  color: #FFF;
}

.footer-score {
  background-color: #ffffffd4;
  color: #2c3e50;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  margin: 0 auto;
  width: 50%;
  height: 60px;
  margin-top: 30px;
}

img {
  width: 150px;
    height: 150px;
    margin: 0 auto;
    margin-top: 10px;
    border: 5px double #577c9c9c;
    border-radius: 10px;
}
</style>
