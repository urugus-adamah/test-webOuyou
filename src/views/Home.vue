<template>
  <div class="home">
    <input type="text" v-model="word">
    <input type="submit" @click="send">
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
    };
  },
  methods :{  
    send(){
      axios
        .post("https://gentle-peak-42861.herokuapp.com/api",{
          id:1,
          data:this.word,
        })
        .then((response)=>{
          console.log(response);
          this.text="testtest";
        });
    }
  } 
};
</script>
