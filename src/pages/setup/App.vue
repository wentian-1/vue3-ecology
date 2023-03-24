<template>
	<SetupDemo ref="son" name='setupDemo' :sum="sum" @handleClick="handleClick">
	</SetupDemo>
	<button @click="sumClick">{{sum}}</button>
</template>

<script setup>
	import {
    onMounted,
		ref
	} from 'vue';
	import SetupDemo from '../src/pages/setup/index.vue';
	let sum = ref(1)
	const sumClick = () => {
		sum.value += 1
	}
	const handleClick = (v) => {
		sum.value += v
	}

	const son = ref(null)
	onMounted(() => {
		console.log(son.value.fun)
	})
	
</script>
