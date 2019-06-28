<template>
    <div class="question-contain">
        <img :src='imgJeux' alt="crash">
        <span class="question">Question {{ indexQuestion }}</span>
        <p>{{ question }}</p>
        <div v-for="(choice, index) in choices" :key="choice" class="container-choice">       
            <span>{{ choice }}</span>
            <input @change="() => verify(index)" v-model="answerModel" :value="choice" type="radio" :name="question">
            <br>
        </div>
    </div>
</template>


<script>

export default {
    name: 'question',
    props: [
        'question',
        'choices',
        'correct',
        'imgJeux',
        'indexQuestion'
    ],
    data() {
        return {
            answerModel: ''
        }
    },
    methods: {
        verify(index) {
            let correct = index === this.correct;

            this.$emit('result', correct);
        }
    }
}
</script>

