<template>
  <button @click="name += '.'">姓名：{{ name }}</button>
  <button @click="age += 1">年龄：{{ age }}</button>
  <button @click="job.job1.salary += 10">薪资：{{ job.job1.salary }}</button>
  <button @click="job.age += 1">工龄：{{ job.age }}</button>
  <button @click="()=>stop()">停止监听</button>
</template>

<script setup>
import { ref, watchEffect, reactive } from "vue";

let name = ref("yfc");
let age = ref(27);

let job = reactive({
  job1: {
    salary: 100,
  },
  age: 10,
});

const stop = watchEffect(() => {
  console.log(name)
  console.log(age)
  console.log(job)
})
</script>