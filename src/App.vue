<template>
	<div id="app">
		<formApp/>
	</div>
</template>

<script>
	import formApp from './components/Form'

	export default {
		name: 'app',
		components: {
			formApp
		}
	}
</script>

<style>
	* {
		font-family: monospace;
	}

	body {
		margin: 0;
		padding: 0;
		background: #813434;
	}

	#app {
		display: block;
	}
</style>