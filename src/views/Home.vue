<template>
  <div class="home">
    <input type="text" v-model="word">
    <input type="submit" @click="send">
    <!-- <p>data1は{{data1}}</p>
    <p>data2は {{data2}}</p> -->
    <p>{{text}}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data(){
    return {
      word:"",
      text:"",
      data1:"",
      data2:""
    };
  },
  methods :{  
    send(){
      axios
        .post("https://gentle-peak-42861.herokuapp.com/api",{data:this.word})
        .then((response)=>{
          this.data1 = response.data;
          this.data2 = response.data.data;
          this.text=response.data.data.data;
        });
    }
  } 
};
</script>
