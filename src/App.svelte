<script lang="ts">
import {converter} from 'culori';
import {onMount} from 'svelte';

	const conv = converter("rgb");
	let canv;
	onMount(()=>{
	    const ctx = canv.getContext('2d');
	    var pixel = ctx.getImageData(0, 0, 400, 400);
	    const data = pixel.data;
	    for (let i=0; i < 400; i++){
	        for (let j=0; j<400;j++){
	           const a = i - 200;
	           const b = j - 200;
	           const r = Math.sqrt(a * a + b * b);
	           const ind = 4 * (400 * i + j);
	           if (r > 200){
	               data[ind]=data[ ind+1]=data[ind+2]=0;
	               data[ ind+3]=1;
	               continue;
	           }
	           
	        }
	    }
	    ctx.putImageData(pixel, 0, 0);
	})
</script>

<main>
    <canvas bind:this={canv} width="400" height="400"  />
	
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
		
	}

    canvas {
      background-color:rgb(233,233,222);
    }
</style>