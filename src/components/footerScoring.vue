<template>
    <div class="footer-score">
        <span>{{ phrase }}</span>
        <span>{{ points }} points</span>
    </div>
</template>

<script>
export default {
    name: "footerScoring",
    props: [
        'points'
    ],
    data() {
        return { 
        // meilleur: 'result1',
        // bon: 'result2',
        // passable: 'result3',
        // mediocre: 'result4',
        // nul: 'result5'
        phrases: [
            'result1', 
            'result2', 
            'result3', 
            'result4', 
            'result5'
        ],
        phrase: 'hello'
        }
    },
    methods: {
        pointsWin() {
            this.phrase = this.phrases[2]
        }
    },
     mounted() {
      console.log(this.phrases[1])
      console.log(this.phrases[0])
  }
}
</script>

