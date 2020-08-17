<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="ง่วงนอนมาแค่ไหน?"/>
    <h1>{{total}}</h1>

    <div class="row"> 
    <!--2. รับค่า emit-->
      <div class="col-3"><Counter lable="ง่วง" @cc="sum" /></div>
      <div class="col-3"><Counter lable="ง่วงนิดๆ" @cc="sum" /></div>
      <div class="col-3"><Counter lable="ง่วงมากกก" @cc="sum" /></div>
      <div class="col-3"><Counter lable="อยากนอนยาวๆ" @cc="sum" /></div>
    
    </div>

    ชื่อ-นามสกุล   <input type="text" v-model="name">
    รหัสนศ. <input type="text" v-model="code">
    GPA <input type="number" v-model="gpa" step="0.01"> 
    <hr>
    แสดง ชื่อ + รหัสนศ + GPA :
    <br/>
    {{name}}  {{code}}  {{gpa}}
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Counter from './components/Counter.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Counter,
  },
  data :function(){
    return{
      total :0, //ผลรวมทั้งหมด--->เอาไปแสดงผล
      name:'',
      code:'',
      gpa:' ',
    }
  },
  methods:{
    //3.คำนวณผลรวมทั้งหทดที่ส่งออกมาจาก emit แล้วเก็บผลรวมไว้ที่ this.total
    // แล้วเก็บผลรวมไว้ที่ this.total
    sum(counterValue) {
      this.total += counterValue


    },
  },
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
</style>
