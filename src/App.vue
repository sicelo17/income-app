<template>
  <Header :totalIncome="state.totalIncome" />
  <Form /> 
</template>

<script>
import { reactive, computed } from 'vue';
import Header from './components/Header';
import Form from './components/Form'

export default {
  setup() {
    const state = reactive({
      income: [],
      totalIncome: computed(() =>{
        let temp = 0;

        if(state.income.length > 0) {
          for (let i = 0; i < state.income.length; i++) {
            temp += state.income[i].value;
          }
        }

        return temp;
      })
    })


    return {
      Header,
      Form,
      state
    }
  }
}
</script>

<style>
* {
  margin: 0;
  box-sizing: border-box;
  padding: 0;
  font-family: 'Fira sans', sans-serif;
}

body {
  background: #eee;
}

</style>
