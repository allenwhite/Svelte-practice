<script>
    import { fly, fade } from 'svelte/transition';

    let visible = true;
</script>

<style>
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
</style>

<label>
    <input type='checkbox' bind:checked={ visible }>
    visible
</label>

{ #if visible }
    <div class="centered" transition:fly={{y: 250}}>
        <span>transitions!</span>
    </div>
{/if}