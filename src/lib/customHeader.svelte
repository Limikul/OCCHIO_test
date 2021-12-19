<title>
    OCCHIO
</title>

<header class='p-9'>
    <div class="float-left">
        <img alt="logo" src="logo.svg"/>
    </div>
    <div class="float-right invisible sm:visible">
        <span class="p-4 font-semibold">Gallery</span>
        <span class="p-4 font-semibold">Contacts</span>
        <img alt="logo2" src="secondary_logo.svg" class="float-right pl-4"/>
    </div>
    <div class="dropdown">
        <button>
            <img alt="options" src="smScreen_options.svg"/>
        </button>
        <div class="shadow invisible absolute right-1 p-1">
            <span class='font-semibold p-2'>Gallery</span><br>
            <span class='font-semibold p-2'>Contacts</span>
        </div>
    <div>
</header>


<style>
    .dropdown {
        @apply visible sm:invisible absolute top-8 right-5 inline-block;
    }

    .dropdown:hover div{
        @apply visible;
    }
</style>


