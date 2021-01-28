<template>
   <header>
       <h1>Income Tracker</h1>
   <div class="total-income">${{ totalIncome }} </div>
   </header>
</template>

<script>
export default {
    props:  {
        totalIncome: Number
    }
}
</script>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 15px 30px;
    background-color: #283747;
    border-bottom: solid 8px #12232e ;
}

header h1 {
    color: #eee;
    font-size: 3rem;
}

header .total-income {
    font-family: 'Fira Code', 'Fira Sans', sans-serif;
    background-color: #007cc7;
    color: #eee;
    font-size: 2rem;
    font-weight: 900;
    padding: .4rem .9rem;
    min-width: 7rem;
    text-align: center;
    border-radius: .8rem;
    box-shadow: inset 0px 0px 6px rgba(0, 0, 0, .25);
    text-shadow: 0px 3px 3px rgba(0, 0, 0, .25);
}
</style>