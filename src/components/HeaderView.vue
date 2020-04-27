<!--https://cn.vuejs.org/v2/style-guide/#%E9%9A%90%E6%80%A7%E7%9A%84%E7%88%B6%E5%AD%90%E7%BB%84%E4%BB%B6%E9%80%9A%E4%BF%A1%E8%B0%A8%E6%85%8E%E4%BD%BF%E7%94%A8-->
<template>
  <!--<button   v-on:click="age += 1">  HeaderView name: {{this.name}} age :{{this.age}}</button >-->
  <!--<button   v-on:click="onclicked">  HeaderView name: {{this.name}} age :{{this.age}}</button >-->
  <button   @click="change">  HeaderView name: {{this.name}} age :{{this.age}}</button >

</template>

<script>
  import { EventBus } from '../main.js'
  export default {
        name: "header-view",
        model: {
          prop: ['name','age'],
        //  event: 'onclicked'
        },
      props: {name:String,age:String},
      data() {
          return {
            // name: "",
            // age:0,
          }
        },
    // computed() {
    //     EventBus.$on('onclicked', param => {
    //       console.log(this.age)
    //       this.age = this.age + 2;
    //     })
    //   },
    computed: {

    },
    methods: {
      onclicked:function() {
        this.age = this.age + 1;
      },
      change:function() {
        this.age = this.age + 1;
        this.$emit('show');//子传父
      },
    }
  }
</script>

<style scoped>

</style>
