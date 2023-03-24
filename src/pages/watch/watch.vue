<template>
  <button @click="name += '.'">姓名：{{ name }}</button>
  <button @click="age += 1">年龄：{{ age }}</button>
  <button @click="job.job1.salary += 10">薪资：{{ job.job1.salary }}</button>
  <button @click="job.age += 1">工龄：{{ job.age }}</button>
  <button @click="()=>stop()">停止监听</button>
</template>

<script setup>
import { onMounted, reactive, ref, watch } from "vue";

let name = ref("yfc");
let age = ref(27);

let job = reactive({
  job1: {
    salary: 100,
  },
  age: 10,
});

watch(name, (name, prevName) => {
  console.log(`name:${name} prevName:${prevName}`);
});

watch(
  () => name.value,
  (name, prevName) => {
    console.log(`name:${name} prevName:${prevName}`);
  }
);

watch([name, age], (newData, oldData) => {
  console.log(`newData:${newData} oldData:${oldData}`);
});

watch(job, (newData, oldData) => {
  console.log(newData, oldData);
});

watch(
  () => job.job1,
  (newData, oldData) => {
    console.log(newData, oldData);
  },
  {
    deep: true,
    immediate: true,
  }
);

const stop = watch(
  () => job.age,
  (newData, oldData) => {
    console.log(newData, oldData);
  }
);

</script>