<template>
  <!-- <h2>FullName - {{firstName}} {{lastName}}</h2>
  <h2>Computed FullName - {{fullname}}</h2>
   <button @click="ChangeFullName">Change Name</button>
   <button @click="items.push({id:4, title: 'keyBoard', price: 50})">Add Item</button>
  <h2>Total computed- {{total}}</h2>
  <h2>Method Total - {{getTotal()}}</h2>
  <input type="text" v-model="country">
   <h2 v-for="item in expensiveItem" :key="item.id">
    {{item.title}} - {{item.price}}
   </h2> -->
  <h2>Volume Tracker (0-20)</h2>
  <h3>Current Volume - {{ volume }}</h3>
  <div>
    <button @click="volume += 2">Increase</button>
    <button @click="volume -= 2">Decrease</button>
  </div>
  <input type="text" v-model="movie" />
  <input type="text" v-model="movieInfo.title" />
  <input type="text" v-model="movieInfo.actor" />
  <div>
    <button @click="movieList.push('Wonder Woman')">Add movie</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      volume: 0,
      movie: "Saber",
      movieInfo: {
        title: '',
        actor: ''
      },
      movieList: ['Batman','Superman']
      // firstName: 'saber',
      // lastName: 'seerat',
      // items: [
      //   {
      //     id: 1,
      //     title: 'TV',
      //     price : 100
      //   },
      //   {
      //     id: 2,
      //     title: 'phone',
      //     price : 200
      //   },
      //   {
      //     id: 3,
      //     title: 'Laptop',
      //     price : 300
      //   },
      // ],
      // country: ''
    };
  },
  methods: {
    //   getTotal(){
    //     console.log('getTotal Method');
    //     return this.items.reduce((total,curr) => (total = total + curr.price),0)
    //   },
    //   ChangeFullName(){
    //     this.fullname = 'Yaser Zahed'
    //   }
    //   },
    // computed:{
    //   fullname: {
    //     get(){
    //       return `${this.firstName} ${this.lastName}`
    //     },
    //     set(value){
    //       const names = value.split(' ')
    //       this.firstName = names[0]
    //       this.lastName = names[1]
    //     }
    //   },
    //   total(){
    //     console.log('Total Computed Property');
    //     return this.items.reduce((total,curr) => (total = total + curr.price),0)
    //   },
    //   expensiveItem(){
    //     return this.items.filter(item => item.price > 100)
    //   }
  },
  computed: {},
  watch: {
    volume(newValue, oldValue) {
      if (newValue > oldValue && oldValue === 16) {
        alert(
          "Listening to a high volume for a long time is damage your hearing"
        );
      }
    },
    movie: {
      handler(newValue) {
        console.log(`Calling API with movie name = ${newValue}`);
      },
      immediate: true
    },
    movieInfo: {
      handler(newValue){
        console.log(
          `Calling API with movie title = ${newValue.title} and actor = ${newValue.actor}`
        );
      },
      deep: true
    },
    movieList: {
      handler(newValue){
        console.log(`Updated List - ${newValue}`);
      },
      deep: true
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
