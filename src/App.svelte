<script lang="ts">
import {converter} from 'culori';

	const conv = converter("rgb");
	const canv;
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

    canvas{
      background-color:rgb(233,233,222);
      }
</style