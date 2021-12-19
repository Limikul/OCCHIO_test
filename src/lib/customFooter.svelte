<script lang='ts'>
    $: outerWidth = 0
</script>

<svelte:window bind:outerWidth/>

<div class='bg-black text-white'>
    <div class="flex">
        <div class='ml-10 sm:ml-36 mr-10'>
            <p class='font-bold text-4xl sm:text-6xl max-w-2xl'>Lorem ipsum dolor sit amet, consectetur adipiscing elit</p>
            <img alt="logo" src="white_logo.svg" class='lg:mt-16 mt-8 mb-20'/>
        </div>
        <div class="flex self-end absolute right-4 sm:right-36 md:right-60 justify-end">
            {#if outerWidth >= 640}
                <img alt="white glasses" src="white_glasses.svg" style="min-width: 168px;" class="opacity-1 w-28 sm:w-52 lg:w-full">
            {:else}
                <img alt="black glasses" src="black_glasses.svg" style="min-width: 168px;" class="opacity-1">
            {/if}
        </div>
    </div>  
</div>
