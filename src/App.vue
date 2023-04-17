<template>
<div>
  <button @click="changePerson">change person!</button>
  <span>{{ person.name }}</span>
  <span>{{ person.age }}</span>
  <br/>
  <button @click="changerPet">change person!</button>
  <span>{{ pet.name }}</span>
  <span>{{ pet.age }}</span>
</div>
</template>

<script>

import {onMounted, ref} from "vue";

export default {
  name: 'App',
  setup() {
    const person = ref({name: 'choi', age: 28});

    const changePerson = () => {
      person.value = {
        name: 'kim',
        age: 30,
      }
    }

    onMounted(() => {
      person.value.name += '(mounted)'
    })

    const pet = ref({type: 'dog', name: 'wondoo'});

    const changerPet = () => {
      pet.value = {
        type: 'cat',
        name: 'woori1',
      }
    }

    onMounted(() => {
      pet.value.name += '(mounted)'
    })

    return { person, changePerson, pet, changerPet }
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
