<script lang="ts">
    import Carousel from "$lib/carousel.svelte";
</script>

<div class="relative flex self-center justify-center translate-x-5 sm:translate-x-0 mb-10 2xl:mt-20 mt-10 ml-0 md:ml-20 lg:ml-52 xl:ml-96 2xl:ml-96 mr-0 sm:mr-8 md:mr-20 lg:mr-28">
    <div class="flex w-5/6 justify-center">
        <img alt="phone frame" src='phone_frame.svg'/>
    </div>
    <Carousel/>
</div>

<style>
    img {
        @apply w-36;
    }

    @media (min-width: 640px) {
        img {
            width: 278px;
        }
    }

    @media (min-width: 768px) {
        img {
            width: 100%;
        }
    }
</style>