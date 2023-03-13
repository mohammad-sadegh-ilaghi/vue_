
<template>
  <div class="home">
    <button @click="decreaseCounter" class="btn">-</button> 
    <span class="counter">{{ counter }}</span>   
    <button @click="increaseCounter" class="btn">+ </button>
  </div>
</template>

<!-- script setup pattern -->
<script setup>
import { ref } from 'vue';
    const counter = ref(0);

    const increaseCounter = () => {counter.value++;};
    const decreaseCounter = ()=> {counter.value--;};
</script>

<!-- setup funtion pattern -->
<!-- <script>
import { ref } from 'vue';
  export default {
    setup(){
      const counter = ref(0);

      const increaseCounter = () => {counter.value++;};
      const decreaseCounter = ()=> {counter.value--;};
      return {
        counter,
        increaseCounter,
        decreaseCounter
      };
    }
  }
</script> -->

<!-- option api-->
<!-- <script>
export default {
  data(){
    return {
      counter : 0
    }
  },
  methods: {
    increaseCounter(){
      this.counter++;
    },
    decreaseCounter(){
      this.counter--;
    }
  }
}

</script> -->
<style>
.home{
  text-align: center; 
  padding: 20px;
}
.counter, .btn {
  font-size: 40px;
}
</style>