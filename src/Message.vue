<template>
  <div>
    <h1></h1>
    <app-input></app-input>
  </div>
</template>

<script>
import Input from './Input.vue';

export default {

data(){
     return {
     message:'this is a great message !',
}
},

components:{
  'app-input':Input
}

}
</script>
