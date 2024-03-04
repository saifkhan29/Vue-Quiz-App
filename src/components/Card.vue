<template>
        <div class="col-12 col-md-4 p-3">
            <div class="card p-3">
                <img class="img-fluid" src="../assets/math.png" alt="">
                <div class="card-text pt-2">
                    <h2>{{ quiz.name }}</h2>
                    <p>{{ quiz.questions.length + 1 }} Questions</p>
                </div>
            </div>
        </div>
</template>

<script setup>
import { defineProps } from 'vue';

const {quiz} = defineProps(['quiz'])
console.log(quiz)

</script>

<style scoped> 
.card{
  background-color: darkcyan;
}

</style>
