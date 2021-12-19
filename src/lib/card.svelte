<script lang="ts">
    import type {carouselItem} from '../ts/carouselItem';
    export let item: carouselItem;
</script>


<img alt="description card" src={item.src} class="card" on:click/>


<style>
    .card {
        width: 101px;
        @apply sm:w-48 md:w-56;
    }

</style>