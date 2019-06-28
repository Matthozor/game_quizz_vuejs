<template>
  <div id="app">
    <!-- <titlepage msg="Game-Quizz"/> -->

    <div class="container">

      <question :indexQuestion="indexQuestion" :question="currentQuestion.label" :choices="currentQuestion.choices"
      :correct="currentQuestion.correct" :imgJeux="currentQuestion.imgJeux" @result="storePoints"/>
    </div>
    <div class="buttonPlacement">
    <button class="buttonQuizz" @click="controlQuizz">Next</button>
    <br>
    <button class="buttonQuizz" @click="restart">Restart</button>
    </div>
    <footerScoring :points="points" />
  </div>
</template>

<script>
import titlepage from './components/title.vue'
import question from './components/question.vue'
import footerScoring from './components/footerScoring.vue'
import 'reset-css';
import { log } from 'util';


export default {
  name: 'app',
  components: {
    titlepage,
    question,
    footerScoring
  },
  computed: {
    currentQuestion() {
      return this.questions[this.currentQuestionIndex];
    }
  },
  methods: {
    storePoints(correct) {
      this.results[this.currentQuestionIndex] = correct;
      // console.log(correct)
      // console.log(this.results);
    },

    controlQuizz () {
      let controlClass = document.querySelector('.hideButton');
      this.ajoutPoint()
      if (this.currentQuestionIndex === this.questions.length - 1) {
        this.fin = true;
        // console.log(controlClass)
      } else {
        this.indexQuestion++
        this.currentQuestionIndex++
      }
    },

    ajoutPoint() {
      this.points = this.results.filter(q => q).length;
    },

    restart() {
      this.fin = this.currentQuestionIndex = this.points = 0;
      this.indexQuestion = 1;
    }
  },
  data() {
    return {
      results: [],
      indexQuestion: 1,
      fin: false,
      points: 0,
      currentQuestionIndex: 0,
      questions: [
        {
          label: 'Que perd Sonic lorsqu\'il est touché ?',
          choices: [
            'Son slip',
            'Des anneaux',
            'Ses poils',
            'Un coeur'
          ],
          correct: 1,
          imgJeux: require('../src/assets/img/sonic.jpeg')
        },

        {
          label: 'Que récolte les petites soeurs dans bioshock ?',
          choices: [
            'Du Mojo',
            'De l\'Adam',
            'Des clopes',
            'De la viande'
          ],
          correct: 1,
          imgJeux: require('../src/assets/img/biosh.jpg')
        },

         {
          label: 'Dans Half-Life l\'arme emblématique est :',
          choices: [
            'Le marteau',
            'Le couteau',
            'Le pied de biche',
            'La cuillère en boé'
          ],
          correct: 2,
          imgJeux: require('../src/assets/img/half.jpg')
        },

         {
          label: 'Comment s\'appelle l\'assistant de professeur Layton ?',
          choices: [
            'Luke',
            'Mr Mouche',
            'Paul',
            'Joe'
          ],
          
          correct: 0,
          imgJeux: require('../src/assets/img/layton.jpg')
        },

         {
          label: 'La phrase que vous verrez le plus dans ce jeu ?',
          choices: [
            '"Fin du jeu"',
            '"Le boss est mort"',
            '"Sauvegarde automatique"',
            '"Vous êtes mort"'
          ],
          correct: 3,
          imgJeux: require('../src/assets/img/darkSoul.jpg')
        },
      {   
          label: 'Quel métier exerce abe ?',
          choices: [
            'Cuisinier',
            'Balayeur',
            'Ingénieur',
            'Gardien'
          ],
          correct: 1,
          imgJeux: require('../src/assets/img/abe.jpeg')
        },

        {
          label: 'Une de ces armes n\'existe pas dans worms, laquelle ?',
          choices: [
            'Justice',
            'Poulet',
            'Pigeon',
            'Vase ming'
          ],
          correct: 1,
          imgJeux: require('../src/assets/img/worms.png')
        },

         {
          label: 'De quel dieux Kratos tient sa puissance et ses lames du chaos ?',
          choices: [
            'Hadès',
            'David',
            'Zeus',
            'Arès'
          ],
          correct: 3,
          imgJeux: require('../src/assets/img/godOf.jpg')
        },

         {
          label: 'Le masque de Jones(Le Crocodile) offre l\'effet :',
          choices: [
            'Le jeu est bien plus sanglant',
            'Vous commencez avec un fusil à pompe',
            'La musique du jeu est différente',
            'Le jeu est en noir et blanc'
          ],
          correct: 0,
          imgJeux: require('../src/assets/img/hotline.jpg')
        },

         {
          label: 'Comment s\'appelle le méchant de l\'histoire ?',
          choices: [
            'Francky Vincent',
            'Helldark',
            'Zarok',
            'Elfarim'
          ],
          correct: 2,
          imgJeux: require('../src/assets/img/medievil.jpg')
        },

        {
          label: 'Comment s\'appelle le fruit dans Crash Bandicoot ?',
          choices: [
            'Mango',
            'Wumpa',
            'Danou',
            'Pomme'
          ],
          correct: 1,
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
          correct: 2,
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
          correct: 0,
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
          correct: 3,
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
          correct: 1,
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
          correct: 3,
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
          correct: 0,
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
          correct: 2,
          imgJeux: require('../src/assets/img/gta.jpg')
        },
           {
          label: 'Les sims avaient pour langage le "Simlish", quelle proposition n\'est pas en Simlish ?',
          choices: [
            'Sul Sul',
            'Cobini !',
            'Ooh be Gah !',
            'Bloo bagoo'
          ],
          correct: 1,
          imgJeux: require('../src/assets/img/sims.png')
        },
           {
          label: 'Dans Dofus, quel dofus est faux ?',
          choices: [
            'Donille',
            'Kaliptus',
            'Vulbis',
            'Cawotte'
          ],
          correct: 0,
          imgJeux: require('../src/assets/img/dofus.jpeg')
        },
           {
          label: 'Dans le dernier mario kart, combien y-a t\'il d\'objet au total ?(Attention les lots de 3 comptent comme un objet)',
          choices: [
            '22',
            '9',
            '15',
            '20'
          ],
          correct: 0,
          imgJeux: require('../src/assets/img/mariokart.jpg')
        },
        {
          label: 'De quel couleur sont les chaussures de Rayman ?',
          choices: [
            'Blanche',
            'Jaune',
            'Rouge',
            'Grise'
          ],
          correct: 1,
          imgJeux: require('../src/assets/img/rayman.jpg')
        },

        {
          label: 'Dans Bubble Bobble un objet permettait d\'augmenter la rapidité de tir :',
          choices: [
            'La lampe',
            'Le bonbon jaune',
            'Le bonbon bleu',
            'Le parapluie'
          ],
          correct: 1,
          imgJeux: require('../src/assets/img/bubble.jpeg')
        },

         {
          label: 'Dans The witcher, Geralt et ses amis sorceleur fondent leur école et lieu de vie à ?',
          choices: [
            'Kaer Adfab',
            'Kaer Solaz',
            'Kaer Guzul',
            'Kaer Morhen'
          ],
          correct: 3,
          imgJeux: require('../src/assets/img/geralt.jpg')
        },

         {
          label: 'Whesker est le méchant de Résident Évil, mais quel est son prénom ?',
          choices: [
            'Joseph',
            'John',
            'Albert',
            'Richard'
          ],
          correct: 2,
          imgJeux: require('../src/assets/img/resident.jpg')
        },

         {
          label: 'Un de ces parcours de SSX TRICKY n\'en est pas un : ',
          choices: [
            'Oclao Flex',
            'Garibaldi',
            'Elysium Alps',
            'Pipe Dream'
          ],
          correct: 0,
          imgJeux: require('../src/assets/img/ssx.jpg')
        },

         {
          label: 'Dans Pokémon, le fameux petit fils du docteur Chen s\'appelle ?',
          choices: [
            'Guillaume',
            'Kevin',
            'Régis',
            'Jacky'
          ],
          correct: 2,
          imgJeux: require('../src/assets/img/pokemon.png')
        },
           {
          label: 'Comment s\'appelle l\'arme de base dans Cuphead ?',
          choices: [
            'Cupshooter',
            'Peashooter',
            'Handshooter',
            'FingerShoot'
          ],
          correct: 1,
          imgJeux: require('../src/assets/img/cuphead.jpg')
        },
           {
          label: 'Dans Heart of Darkness, Andy se rend à DarkLands pour retrouver :',
          choices: [
            'Son chien',
            'Son grand-père',
            'Sa soeur',
            'Bénédicte'
          ],
          correct: 0,
          imgJeux: require('../src/assets/img/heartOf.jpg')
        },
           {
          label: 'Dans le fabuleux jeu Tétris, combien y-a t\'il de forme ?',
          choices: [
            '5',
            '9',
            '6',
            '7'
          ],
          correct: 3,
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
  font-size: -webkit-xxx-large;
}
.container {
  background-color: #ffffffbd;
  border-bottom: 3px solid #FFF;
  border-top: 3px solid #FFF;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  margin: 0 auto;
  width: 50%;
  margin-bottom: 25px;
  margin-top: 25px;
}
.question {
    margin-top: 13px;
    color: white;
    border-radius: 10px;
    border-bottom: 3px solid #FFF;
    background-color: #3c546d;
    width: 50%;
    height: 40px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: center;
}
.container p {
  background-color: #577c9c9c;
  color: #FFF;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 60px;
  margin-top: 15px;
  margin-bottom: 15px;
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

.hideButton {
  display: none;
}
.buttonPlacement {
    display: flex;
    flex-direction: row;
    justify-content: center;
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
  margin-right: 10px;
  margin-left: 10px;
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
  background-color: #FFF;
  margin-bottom: 10px;
}
</style>
