<template>
    <h1>{{greeting}} {{name}}</h1>
    <h2 v-text="lastname"></h2>
    <h2 v-html="channel"></h2>
    <h2 v-bind:id="headindId">Heading</h2>
    <button v-bind:disabled="isDisabled">Bind</button>
    <h2 class="underlined">Underlined text</h2>
    <h2 class="underlined" v-bind:class="status">status</h2>
    <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>
    <h2 v-bind:class="isSoldOut ? 'sold-out' : 'new'">SoldOut Movie</h2>
    <h2 v-bind:class="['new','promoted']">Newly promoted Movie</h2>
    <h2 v-bind:class="[isPromoted && 'promoted', isSoldOut ? 'sold-out' : 'new']">Array conditional Movie</h2>
    <h2 v-bind:class="{
      promoted: isPromoted,
      new: !isSoldOut,
      'sold-out': isSoldOut
    }">Object conditional Movie</h2>
    <h2 v-bind:style="{
      color: highlightColor,
      fontSize: headerSize + 'px',
      padding: '20px'          //static value
    }">Inline Style</h2>
    <h2 v-bind:style="headerStyleObject">Style Object</h2>

    <div v-bind:style="[baseStyleObject,successStyleObject]">Success Style</div>
    <div v-bind:style="[baseStyleObject,dangerStyleObject]">Danger Style</div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return{
      greeting: 'Hello',
      name: 'saber',
      lastname: 'seerat',
      channel: '<b>Lajaward</b>',
      headindId : 'heading',
      isDisabled: true,
      status: 'danger',
      isPromoted:  true,
      isSoldOut: true,
      highlightColor: 'orange',
      headerSize: 50,
      headerStyleObject:{
        color: 'orange',
        fontSize: '50px',
        padding: '20px'
      },
      baseStyleObject:{
        fontSize: '50px',
        padding: '10px',
      },
      successStyleObject:{
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px solid green',
        padding: '20px'
      },
      dangerStyleObject:{
        color: 'darked',
        backgroundColor: 'red',
        border: '1px solid darked'
      }
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
.underlined {
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
}
</style>
