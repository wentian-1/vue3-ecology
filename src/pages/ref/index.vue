<template>
  <p>姓名: {{ name }}</p>
  <p>年龄: {{ age }}</p>
  <div>
    <h3>工作信息</h3>
    <p>职业:{{ job.post }}</p>
    <p>薪资:{{ job.salary }}</p>
  </div>
  <p>数组:{{ JSON.stringify(arr) }}</p>
  <button @click="raiseSalary">涨薪</button>
</template>
<script>
import { reactive } from "vue";
import { ref } from "vue";
export default {
  setup() {
    let name = ref("yfc");
    let age = ref(27);
    // let job = ref({
    //   post: "前端开发",
    //   salary: 10,
    // });
		let job = reactive({
		  post: "前端开发",
		  salary: 10,
		});
    let arr = ref([0, 1, 2, 3]);
    const raiseSalary = () => {
      job.salary += 10;
      age.value += 1;
      arr.value[2] = 4;
    };
    return {
      name,
      age,
      job,
      raiseSalary,
      arr
    };
  },
};
</script>