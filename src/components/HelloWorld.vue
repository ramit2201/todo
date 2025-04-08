<template lang="pug">
  div
    h1 Hello {{ name }}
    input(v-model="name" placeholder="Type your name")
    button(@click="greet") Greet
  </template>
  
  <script>
  export default {
    data() {
      return {
        name: ''
      };
    },
    methods: {
      greet() {
        alert(`Hi, ${this.name || 'stranger'}!`);
      }
    }
  };
  </script>
  