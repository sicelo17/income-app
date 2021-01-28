<template>
  <form action="">
      <input type="text" placeholder="Description...">
      <input type="number" placeholder="Value...">
      <input type="date" placeholder="Date">
      <input type="submit" value="Submit">
  </form>
</template>

<script>

import { reactive } from 'vue';

export default {
    props: {
        state: Object
    },
    setup(props, { emit }){
        
    }
}
</script>

<style scoped>
form {
    display: flex;
    justify-content: center;
    margin-top: 3rem;
}

form input {
    color: #888;
    border: none;
    outline: none;
    font-size: 1.5rem;
}

form input::placeholder {
    color: #aaa;
}

form input::not([type="submit"]){
    display: block;
    background-color: #fff;
    border: none;
    outline: none;
    padding: 5px 15px;
    margin-left: 10px;
}

form input[type="submit"] {
    display: block;
    background: none;
    outline: none;
    color: #fff;
    font-weight: 500;
    text-shadow: 0px 1px 3px rgba(0, 0, 0, .2);
    padding: 5px 15px;
    cursor: pointer;
    background-color: #007cc7;
}

form input:first-of-type {
    border-radius: 8px 0px 0px 8px ;
}

form input:last-of-type {
    border-radius: 0px 8px 8px 0px;
}


</style>