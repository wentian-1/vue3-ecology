<template>
  <p>区号<input v-model="phone.first" /></p>
  <p>座机号<input v-model="phone.two" /></p>
  <p>完整号码<input v-model="finallPhone2" /></p>
</template>

<script setup>
import { computed, reactive } from "vue";

let phone = reactive({
  first: "",
  two: "",
});

let finallPhone = computed(() => phone.first + "-" + phone.two);
finallPhone.value ++

let finallPhone2 = computed({
  get: () => phone.first + "-" + phone.two,
  set: (value) => {
    if (value && value.includes('-')) {
      const arr = value.split('-')
      phone.first = arr.shift()
      phone.two = arr.join('')
    }
  }

});

</script>