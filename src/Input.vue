<template>
  <div>
    <input type="text" v-model="message" />

    <h1>this is a great {{ message }} !</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: ""
    };
  }
};
</script>
