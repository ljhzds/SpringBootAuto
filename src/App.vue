<template>
	<div id="app">
		<img alt="Vue logo" src="./assets/logo2.png">
		<!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
		<UploadExcel></UploadExcel>
	</div>
</template>

<script>
	// import HelloWorld from './components/HelloWorld.vue'
	import UploadExcel from './components/UploadExcel.vue'

	export default {
		name: 'app',
		components: {
			// HelloWorld, 
			UploadExcel
		}
	}
</script>

<style>
	#app {
		font-family: 'Avenir', Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		color: #2c3e50;
		margin-top: 60px;
	}
</style>
