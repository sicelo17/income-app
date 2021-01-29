<template>
  <Form @add-income="AddIncome" /> 
  <IncomeList :state="state" />
</template>

<script>
import { reactive, computed } from 'vue';
import Form from '../components/Form'
import IncomeList from '../components/IncomeList'

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
      }),
      
      sortedIncome: computed(() => {
        let temp = [];

        // eslint-disable-next-line vue/no-side-effects-in-computed-properties
        temp = state.income.sort(function (a, b) {
          return b.date - a.date;
        });

        return temp;
      })
    });

    function AddIncome(data){
      let d = data.date.split("-");
      let newD = new Date(d[0], d[1], d[2]);

      state.income = [...state.income, {
        id: Date.now(),
        desc: data.desc,
        value: parseInt(data.value),
        date: newD.getTime()
      }];
      console.log(state.income);
    }


    return {
      Form,
      IncomeList,
      state,
      AddIncome
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
