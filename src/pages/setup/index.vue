<template>
<!-- 	<span>姓名:{{name}}</span>
	<button @click="say">say</button> -->
<!-- 	<p>
		<span>props.name：{{name}} </span>
	</p>
	<p>
		<span>props.sum：{{sum}} </span>
	</p> -->
	
	<!-- <p>
		attrs: {{ isEven === 1  ? '奇数' :'偶数'}}
	</p> -->

	<p>emits <button @click="onClick">点击调用父方法</button></p>

</template>


	// import {
	// 	h
	// } from 'vue'
	// export default {
	// 	beforeCreate() {
	// 		console.log('beforeCreate')
	// 	},
	// 	setup() {
	// 		console.log('setup')
	// 		const name = 'yfc'
	// 		const say = () => {
	// 			console.log(`hello${name}`)
	// 		}
	// 		// return () => h('div', {
	// 		// 	class: 'div'
	// 		// }, [
	// 		// 	h('h2', 'hello')
	// 		// ])
	// 		return {
	// 			name,
	// 			say
	// 		}
	// 	}
	// }



// import { toRef } from 'vue'

// export default {
// 	props: {
// 		name: String,
// 		sum: Number
// 	},
// 	setup(props) {
// 		const sum = toRef(props, "sum")
// 		return {
// 			name: props.name,
// 			sum
// 		}
// 	}
// }

// import { ref } from 'vue';
// import { onBeforeUpdate } from 'vue'
// export default {
// 	setup(props, { attrs}) {
// 		let isEven = ref(1)
// 		onBeforeUpdate(() => {
// 			const sum = attrs.sum
// 			if (sum % 2 === 0) {
// 				isEven.value = 2
// 			} else {
// 				isEven.value = 1
// 			}
// 		})
// 		return {
// 			isEven
// 		}
// 	}
	
// }



<!-- <script>
	export default {
		setup(props, { slots }) {
			console.log(slots)
		}
	}
</script> -->

<script>
 export default {
	setup(props, { emit, expose }) {
		const onClick = () => {
			emit('handleClick', 10)
		}
		expose({fun: onClick})
		return {
			onClick
		}
	}
 }
</script>
