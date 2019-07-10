<script>
    import { fly, fade, draw } from 'svelte/transition';
    export const transitions = { draw };
    let visible = true;
</script>

<style>
    .bottom {
        position: absolute;
        left: 50%;
        top: 250%;
        transform: translate(-50%, -50%);
    }
    .centered {
        position: absolute;
        left: 50%;
        top: 150%;
        transform: translate(-50%, -50%);
    }

    span {
        position: absolute;
        transform: translate(-50%, -50%);
        font-size: 4em;
    }

    svg {
		width: 100%;
        position: absolute;
        left: 25%;
        top: 300%;
	}
	
	path {
		fill: none;
		stroke: rgb(111,11,111);
		stroke-width: 2px;
	}
</style>

<label>
    <input type='checkbox' bind:checked={ visible }> visible
</label>

{ #if visible }
    <div class="bottom" transition:fly={{y: 250}}>
        <span>!FLY!</span>
    </div>

    <div class="centered" transition:fade>
        <span>_F_A_D_E_</span>
    </div>

{/if}

<svg viewBox='0 0 100 100'>
  {#if visible}
    <path d="M10,10 L40,10 40,20 10,20 Z" transition:draw/>
  {/if}
</svg>