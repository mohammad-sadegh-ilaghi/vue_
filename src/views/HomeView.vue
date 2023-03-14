
<template>
  <h3>{{ countData.title  }}</h3>
  <div class="home">
    <button @click="decreaseCounter(1, $event)" class="btn">-</button> 
    <button @click="decreaseCounter(2, $event)" class="btn">--</button> 
    <span class="counter">{{ countData.count }}</span>   
    <button @click="increaseCounter(2, $event)" class="btn">++ </button>
    <button @click="increaseCounter(1, $event)" class="btn">+ </button>
  </div>
  <p>this number is {{ oddOrEven }}</p>
  <div class="edit">
    <h4>edit Counter title</h4>
    <input v-model="countData.title" type="text" >
  </div>
</template>

<!-- script setup pattern -->
<script setup>
import { ref, reactive, computed } from 'vue';

    // ref data
    const counter_noneReactive = ref(0), 
           counterTitle_noneReactive = ref('My Counter');
    // reactive data
    const countData = reactive({
      count: 0,
      title: 'My Counter'
    });

    // computed in vue
    const oddOrEven = computed(()=>{
      if(countData.count % 2 == 0) return "odd";
      return "even";
    });
    // non reactive data 
    const counter = 0, counterTitle = "my counter";

    // methods
    const increaseCounter = (amount, e) => {countData.count += amount;};
    const decreaseCounter = (amount, e)=> {countData.count -= amount;};
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