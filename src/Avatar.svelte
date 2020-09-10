<script>
	import {onMount} from 'svelte/internal'
	export let alt = 'A'
	export {klass as class}

	// override classes
	let klass = 'text-xl rounded-full text-white'
	
	export let size = 12
	export let bg = 'orange-500'
	export let src = null

	onMount(() => {
		if(src){
			let img = new Image()
			img.src = src
			img.onerror = () => {
				src = null
			}
		}
	})

	let round_class = ''

	$:if(klass){
		round_class = klass.split(' ').find(c => c.startsWith('rounded'))||''
	}


</script>


<div class="flex relative w-{size} h-{size} bg-{bg} justify-center items-center m-1 mr-2 {klass}" key="k2">
		{#if src}
			<img class="{round_class}" {alt} {src} />
		{:else}
			<slot>
					{alt[0]}
			</slot>
		{/if}
		<slot name="badge">
		</slot>
</div>