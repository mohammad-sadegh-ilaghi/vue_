
<template>
  <h3>{{ countData.title  }}</h3>
  <div class="home">
    <button @click="decreaseCounter" class="btn">-</button> 
    <span class="counter">{{ countData.count }}</span>   
    <button @click="increaseCounter" class="btn">+ </button>
  </div>

  <div class="edit">
    <h4>edit Counter title</h4>
    <input v-model="countData.title" type="text" >
  </div>
</template>

<!-- script setup pattern -->
<script setup>
import { ref, reactive } from 'vue';

    // ref data
    const counter = ref(0), 
           counterTitle = ref('My Counter');
    // reactive data
    const countData = reactive({
      count: 0,
      title: 'My Counter'
    });

    // non reactive data 
    const counter = 0, counterTitle = "my counter";

    // methods
    const increaseCounter = () => {countData.count++;};
    const decreaseCounter = ()=> {countData.count--;};
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
.edit {
  margin-top: 60px;
}
</style>