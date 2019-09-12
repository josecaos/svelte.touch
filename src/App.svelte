<script>
	import DragDrop from './componentes/DragDrop.svelte'
	import './main.css'
	export let name;
</script>
<!--  -->
<style>
	/* h1 {
		color: purple;
	} */
</style>
<!--  -->
<h1>{name}!</h1>

<section>
	<DragDrop />
</section>
