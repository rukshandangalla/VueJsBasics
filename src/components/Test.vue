﻿<template>
    <div class="test">
        <input type="text" v-model="title"><br/>
        <h1>{{title}}</h1>
        <p v-if="showName">{{user.firstName}}</p>
        <p v-else>Nobody</p>
        <ul>
            <li v-for="item in items">{{item.title}}</li>
        </ul>
        <br/>

        <button v-on:click="greet('Hi')">Say Greeting</button>
        <br/>

        <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="pressEnter"><br/>
    </div>
</template>

<script>
  export default {
    name : 'test',
    data(){
        return{
            title: 'Hello World',
            user:{
            firstName: 'John',
            lastName: 'Doe',
        },
        showName: true,
        items: [
            {title: 'Item One'},
            {title: 'Item Two'},
            {title: 'Item Three'}
            ]
        }
    },
    methods: {
        greet: function(message){
            alert(message);
        },
        pressKey: function(e){
            console.log(e.target.value);
        },
        pressEnter: function(e){
            console.log("Press Enter");
        }
    }
  }
</script>

<style scoped>

</style>