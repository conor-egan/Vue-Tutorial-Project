<template>

  <div class="test">
    <input type="text" v-model="title"><br/>
    <h1>{{title}}</h1>
    <p v-if="showName">{{user.firstName}}</p>
    <p v-else="showName">Nobody</p>
    <p v-if="showName">{{user.lastName}}</p>
    <ul>
      <li v-for="item in items">{{item.title}}</li>
    </ul>
    <button v-on:click="greet('Hello World')">Say Greeting</button><br/>
    <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">
    <hr/>
    <label>First Name: </label><input type="text" v-model="user.firstName">
    <br/>
    <label>Last Name: </label><input type="text" v-model="user.lastName">
    <h3>{{fullname}}</h3><br/>
    <h2>{{msg}}</h2>
  </div>
</template>


<script>
  export default{
    name: 'test',
    props: {
      msg: {
        type: String,
        default: 'Empty message'
      }
    },
    data(){
      return {
        title: 'Hello World',
        user: {
          firstName: "John",
          lastName: 'Doe'
        },
        showName: true,
        items: [
        {title: 'item1'},{title: 'item2'},{title: 'item3'}
        ]
      }
    },
    methods: {
      greet: function(greeting){
        alert(greeting);
      },
      pressKey: function(e){
        console.log(e.target.value);
      },
      enterHit: function(){
        console.log('You hit enter');
      }
    },
    computed: {
      fullname: function(){
        return this.user.firstName + ' '+this.user.lastName;
      }
    }
  }
</script>

<style scoped>

</style>
