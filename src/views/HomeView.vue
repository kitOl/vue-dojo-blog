<template>
  <div class="home">
    home
    <p ref="p">My name is {{ name.toUpperCase() }} and my age is {{ age }}</p>
    <button @click="handleClick">click me</button>
  </div>
</template>

<script>
import { ref } from 'vue';

// @ is an alias to /src

export default {
  name: 'HomeView',
  setup() {
    console.log(this);

    const p = ref('hello');

    let name = 'mario';
    let age = 30;

    const handleClick = () => {
      console.log(p, p.value);
      p.value.classList.add('test');
      p.value.textContent = 'hello, ninjas';
    };

    return { name, age, handleClick, p };
  },
};
</script>
