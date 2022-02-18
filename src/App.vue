<template>
  <div id="app">
    <h1>search select</h1>

    <div class="select-item" @click="isVisible = !isVisible">
      <span v-if="selectitem"> {{selectitem.name}}</span>
     
      <span v-else> select user   <strong>   {{ isVisible ? 'V' : '^' }}</strong> </span>
    </div>
    
    <div class="dropdown" v-if="isVisible">
      <input v-model="searchQuery" type="text" placeholder="search" />
      <span v-if="filterTask.length ===0 "> no such task</span>

      <span class="options">
        <ul>
          <li  @click="selectedItem(user) " v-for="(user, index) in filterTask" :key="index" :index="index"  >
            {{ user.name }}
          </li>
        </ul>
      </span>
    </div>
  </div>
</template>

<script>


export default {

  name: "app",


  data() {
    return {
      searchQuery: "",
      selectitem: null,
      isVisible: false,
      slides: [
        { name: "benjamin" },
        { name: "robert" },
        { name: "ayman" },
        { name: "emeline" },
        { name: "rwanda" },
        { name: "uganda" },
        { name: "kenya" },
        { name: "tanzania" },
        { name: "burundi" }
      ]
    };
  },
  
  computed: {
    filterTask() {
      const query = this.searchQuery.toLowerCase();

      if (this.searchQuery === "") {
        return this.slides;
      }
      return (this.query = this.slides.filter(user => {
        return Object.values(user).some((word) => 
          String(word)
            .toLowerCase()
            .includes(query)
        );
      }));
    }
  },
  methods:{
    selectedItem(user) {
      this.selectitem = user;
      this.isVisible=false;
    }
  },
  
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

ul {

  list-style-type: none;
  padding: 0;
  overflow-y: scroll;
  overflow-x: hidden;
  border: 2px solid black;
}

li {
  
  margin: 0 10px;
  border-bottom: 2px solid black;
  color: black;
  cursor: pointer;
}
li:hover {
  background-color: grey;
}

.slide-image {
  display: flex;

  flex-direction: column;
}
.input {
  width: 5rem;
}
.dropdown {
  border: 1px solid black;
  background-color: bisque;
}
.select-item {
  border: 1px solid black;
}
</style>
