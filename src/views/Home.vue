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
      console.log("enter_send");
      axios
        .post("https://gentle-peak-42861.herokuapp.com/api",{
          data:this.word,
        })
        .then((response)=>{
          // console.log(response);
          this.text=response.data.data;
        });
        console.log("out_send");
    }
  } 
};
</script>
