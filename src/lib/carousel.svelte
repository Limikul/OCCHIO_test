<script lang="ts">
    import Card from '$lib/card.svelte'
    import { getContext } from 'svelte';    
    import type {carouselItem} from '../ts/carouselItem';

    let turnCarousel: (item: carouselItem, carousel: HTMLElement) => void = getContext('turnCarousel');
    let carouselItems: carouselItem[] = getContext('carouselItems');
        
    let carousel;
    let card;
</script>

<div class="carousel" bind:this={carousel}>
    {#each carouselItems as item}
        <Card item={item} on:click={() => turnCarousel(item, carousel)} />
    {/each}
</div>


<style>
    .carousel { 
        @apply absolute flex flex-row w-full self-center justify-center translate-x-1 -translate-y-4 sm:-translate-y-8 md:-translate-y-9 gap-1 sm:gap-3 transition-all;
        width: 500px;
    }

</style>