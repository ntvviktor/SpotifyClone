<script>
    import Icon from '@iconify/svelte'
    import { audioPlayer, isPlaying} from '$lib/data';
    function playAudio() {
        //@ts-ignore
        $audioPlayer.play();
        $isPlaying = true;
    }
    function pauseAudio() {
        //@ts-ignore
        $audioPlayer.pause();
        $isPlaying = false;
    }
</script>
{#if $isPlaying === false}
<button on:click={playAudio} id="play">
    <Icon icon="gridicons:play" width="40" color="#00A693"></Icon>
</button>
{:else}
<button on:click={pauseAudio} id="pause">
    <Icon icon="ic:baseline-pause" width="40" color="#00A693"></Icon>
</button>
{/if}

<style>
    button {
        background-color: transparent;
        border: none;
        margin: 0;
        padding: 0;
        border-radius: 0;
    }
</style>


