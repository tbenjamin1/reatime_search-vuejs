<template>
  <div class="carousel" >
  <slot></slot>
    

<button class='Next-button' @click="next" >Next</button>
<a class="previous-button" @click="previous" >Prev</a>

  </div>
</template>

<script>
export default {



  data() {
    return {
  
    };
  },
  methods: {
    next() {
       this.$emit('next')
    },
    previous(){
         this.$emit('previous')
      
    }
  },


};
</script>

<style>
.carousel{

  position:relative;
  width:600px;
  height:350;
  overflow:hidden;
}
button{
  position:absolute;
  height:40px;
  width:50px;
  top:calc(50% - 20px);
  border:none;
  background-color:black;
  padding:2px;
  color:white;
  border-radius:50px;
  left:7px;
}
button:active, button:hover{
  outline:none;
  cursor:pointer;
    background-color:white;
    color:black;
}
.Next-button{

}
.previous-button{
  left:0;
}
a {
  color: #42b983;
    right:0;
    
}

</style>
