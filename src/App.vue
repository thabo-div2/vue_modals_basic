<template>
	<h1>{{ title }}</h1>
	<!-- <input type="text" ref="name" />
	<button @click="handleClick">Click Me</button> -->
	<teleport to=".modals" v-if="showModal">
		<Modal theme="sale" @close="toggleModal">
			<h1>Welcome...</h1>
			<p>Get new swords today!!</p>
			<template v-slot:links>
				<a href="#">Boom!</a>
				<a href="#">Pow!</a>
			</template>
		</Modal>
	</teleport>
	<p>Open Modal</p>
	<button @click="toggleModal">Open Modal</button>
	<teleport to=".modals" v-if="showModalTwo">
		<Modal @close="toggleModalTwo">
			<h1>I did this</h1>
			<p>This is my modal</p>
		</Modal>
	</teleport>
	<p>Open my Modal</p>
	<button @click="toggleModalTwo">Open My Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
	name: "App",
	components: { Modal },
	data() {
		return {
			title: "My First Vue App",
			showModal: false,
			showModalTwo: false,
		};
	},
	methods: {
		// handleClick() {
		// 	console.log(this.$refs.name);
		// 	this.$refs.name.classList.add("active");
		// 	this.$refs.name.focus();
		// },
		toggleModal() {
			this.showModal = !this.showModal;
		},
		toggleModalTwo() {
			this.showModalTwo = !this.showModalTwo;
		},
	},
};
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
h1 {
	border-bottom: 1px solid #ddd;
	display: inline-block;
	padding-bottom: 10px;
}
</style>
