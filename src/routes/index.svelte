<script lang="ts">
    import CustomHeader from '$lib/customHeader.svelte';
    import UpperHalf from '$lib/upperHalf.svelte';
    import Button from '$lib/button.svelte';
    import LowerHalf from '$lib/lowerHalf.svelte';
    import CustomFooter from '$lib/customFooter.svelte';
    import type {carouselItem} from '../ts/carouselItem';
    import { setContext } from 'svelte';

    let current: number = 2;
    let carouselItems: carouselItem[] = [{src: 'card1.svg', id: 1}, {src: 'card2.svg', id: 2}, {src: 'card3.svg', id: 3}];

    let turnCarousel = (item: carouselItem, carousel: HTMLElement): void => {

        if (item.id == current) return;
        else {
            var cards: HTMLCollectionOf<HTMLImageElement> = carousel.getElementsByTagName('img');
            Array.from(cards).map(c => c.style.visibility = "visible");
            let style: CSSStyleDeclaration = window.getComputedStyle(carousel);
            var matrix: DOMMatrix = new WebKitCSSMatrix(style.transform);
            var card: Element = carousel.firstElementChild;
            var move: number = card.clientWidth;

            if (outerWidth < 640) var gap: number = 4;
            else var gap: number = 12;
        }

        if (current > item.id) {
            let coef: number = current - item.id;
            carousel.style.transform = "translate(" + (((move + gap)*coef) + matrix.e) + "px ," + matrix.f + "px)";
            
        }

        else if (current < item.id) {
            let coef: number = item.id - current;
            carousel.style.transform = "translate(" + ((-(move + gap)*coef) + matrix.e) + "px ," + matrix.f + "px)";
        }
        
        current = item.id;
        console.log(current);
        console.log(cards);

        if (cards[current - 3] != undefined) {
            cards[current - 3].style.visibility = "hidden"
        }
        
        if(cards[current + 1] != undefined) {
            cards[current + 1].style.visibility = "hidden"
        }
        
    } 

    setContext('turnCarousel', turnCarousel);
    setContext('carouselItems', carouselItems);

    $: innerWidth = 0

    let resize = () => {
        current = 2;
        let carousel: HTMLElement = Array.from(document.getElementsByClassName("carousel") as HTMLCollectionOf<HTMLElement>)[0];
        let cards: HTMLCollectionOf<HTMLImageElement> = carousel.getElementsByTagName('img');
        Array.from(cards).map(c => c.style.visibility = "visible");

        if (innerWidth < 640) carousel.style.transform = "translate(" + 1.75 + "px," + -16 + "px)";
        else if (innerWidth < 768) carousel.style.transform = "translate(" + 1.75 + "px," + -32 + "px)";
        else carousel.style.transform = "translate(" + 1.75 + "px," + -36 + "px)";
    }
</script>

<svelte:window bind:innerWidth on:resize={resize}/>

<CustomHeader/>
<UpperHalf/>
<Button/>
<LowerHalf/>
<CustomFooter/> 
