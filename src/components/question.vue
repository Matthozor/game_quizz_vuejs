<template>
    <div class="question-contain">
        <img :src='imgJeux' alt="crash">
        <p>{{ question }}</p>
        <div v-for="choice in choices" :key="choice" class="container-choice">       
            <span>{{ choice }}</span>
            <input @change="verify" v-model="answerModel" :value="choice" type="radio" :name="question">
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
        'imgJeux'
    ],
    data() {
        return {
            answerModel: ''
        }
    },
    methods: {
        verify() {
            console.log(this.answerModel)
        }
    }
}
</script>

