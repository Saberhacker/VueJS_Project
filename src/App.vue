<template>
    <!-- <h1>{{greeting}} {{name}}</h1>
    <h2 v-text="lastname"></h2>
    <h2 v-html="channel"></h2>
    <h2 v-bind:id="headindId">Heading</h2>
    <button v-bind:disabled="isDisabled">Bind</button>
    <h2 class="underlined">Underlined text</h2>
    <h2 class="underlined" v-bind:class="status">status</h2>
    <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>
    <h2 v-bind:class="isSoldOut ? 'sold-out' : 'new'">SoldOut Movie</h2>
    <h2 v-bind:class="['new','promoted']">Newly promoted Movie</h2>
    <h2 v-bind:class="[isPromoted && 'promoted', isSoldOut ? 'sold-out' : 'new']">Array conditional Movie</h2> -->
    <!-- <h2 v-bind:class="{
      promoted: isPromoted,
      new: !isSoldOut,
      'sold-out': isSoldOut
    }">Object conditional Movie</h2>
    <h2 v-bind:style="{
      color: highlightColor,
      fontSize: headerSize + 'px',
      padding: '20px'                                                                        
    }">Inline Style</h2>
    <h2 v-bind:style="headerStyleObject">Style Object</h2> -->

    <!-- <div v-bind:style="[baseStyleObject,successStyleObject]">Success Style</div> -->
    <!-- <div v-bind:style="[baseStyleObject,dangerStyleObject]">Danger Style</div> -->
    <!-- <h2 v-if="num == 0">The number is zero</h2>
    <h2 v-else-if="num < 0">The number is negative</h2>
    <h2 v-else-if="num > 0">The number is positive</h2>
    <h2 v-else>Not a number</h2>
    <template v-if="display">
      <h2>Saber.Seerat</h2>
      <h2>Lajaward</h2>
      <h2>Vue JS</h2> -->
    <!-- </template> -->
    <!-- <h2 v-for="(name,index) in names" :key='name'>{{index}} {{name}}</h2>
    <h2 v-for="name in fullname" :key="name.first">{{name.first}} {{name.last}}</h2>
    <h3 v-for="(value,key,index) in myInfo" :key="value.name">{{index}} {{key}} {{value}}</h3> -->
    <!-- <template v-for="name in names" :key="name">
      <h2 v-if="name === 'saber'">{{name}}<hr></h2>
    </template> -->
    <!-- <h2>Add method - {{add(2,3,5)}}</h2>
    <h2>Add method - {{multiplay(10)}}</h2>
    <h2>Add method - {{multiplay(arrValue)}}</h2> -->
    <h1>{{name}}</h1>
    <div>
      <button @click="changeName($event), increment(1,$event)">Change Name</button>  
      <!-- multiple event handler -->
    </div>
    <h2>{{count}}</h2>
    <button @click="increment(1,$event)">increment</button>
    <button @click="decrement(1)">decrement</button>
    <button @click="increment(5)">increment 5</button>
</template>

<script>
export default {
  name: 'App',
  data() {
    return{
      basevalue: 5,
      arrValue: 2,
      names: ['saber','seerat','samim'],
      fullname :[
        {first: "saber",last: 'seerat'},
        {first: "yaser",last: 'zahed'},
        {first: "seyar",last: 'samim'},
      ],
      myInfo: {
        name: 'saber',
        channel: 'Lajaward',
        course : 'VueJS'
      },
      name: 'Saber',
      count: 0
      // num: 'd',
      // display: true
      // greeting: 'Hello',
      // name: 'saber',
      // lastname: 'seerat',
      // channel: '<b>Lajaward</b>',
      // headindId : 'heading',
      // isDisabled: true,
      // status: 'danger',
      // isPromoted:  true,
      // isSoldOut: true,
      // highlightColor: 'orange',
      // headerSize: 50,
      // headerStyleObject:{
      //   color: 'orange',
      //   fontSize: '50px',
      //   padding: '20px'
      // },
      // baseStyleObject:{
      //   fontSize: '50px',
      //   padding: '10px',
      // },
      // successStyleObject:{
      //   color: 'green',
      //   backgroundColor: 'lightgreen',
      //   border: '1px solid green',
      //   padding: '20px'
      // },
      // dangerStyleObject:{
      //   color: 'darked',
      //   backgroundColor: 'red',
      //   border: '1px solid darked'
      // }
    }
  },
  methods:{
    add(a,b,c){
      return a+b+c
    },
    multiplay(num) {
      return num * this.basevalue
    },
    changeName(event){
      this.name = "Batman"
      console.log('Event',event);
    },
    increment(num,event){
       this.count += num
       console.log('Event',event);
    },
    decrement(num){
       this.count -= num
    }
  }
}
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
/* .underlined {
  text-decoration: underline;
}
.promoted{
  font-style: italic;
}
.new {
  color: olivedrab;
}
.sold-out {
  color: red;
} */
</style>
