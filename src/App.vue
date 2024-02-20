<template>
  <div>
    <div class="container pt-5">
      <div class="row">
        <div class="col-12 d-flex">
          <header class="me-4"><h1>Quizes</h1></header>
          <input v-model.trim="search" class="align-self-center p-1 px-2" type="text" placeholder="Search..." name="" id="">
        </div>
      </div>
    </div>
    <div class="container">
      <div class="row options-container py-4 gx-4">
      <div class="col-12 col-md-4 p-3" v-for="quiz in quizes" :key="quiz.id">
        <div class="card p-3">
          <img class="img-fluid" src="./assets/math.png" alt="">
          <div class="card-text pt-2">
            <h2>{{ quiz.name }}</h2>
            <p>{{ quiz.questions.length + 1 }} Questions</p>
          </div>
        </div>
      </div>
    </div>
    </div>
  </div>
</template>

<script setup>
  import { ref,watch } from "vue"
  import q from "./data/data.json"
  const search = ref("")
  const quizes = ref(q)

watch(search, () => {
  quizes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()))
})


</script>

<style scoped>
h1{
  font-size: 32px;
}

.card{
  background-color: darkcyan;
}
  
</style>