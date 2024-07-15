<script>
    import { Article } from '$lib/index.js';
    import Siema from 'siema';
    import { onMount } from "svelte";

    let slider, prev, next
    let select = 0

    onMount(() => {
        slider = new Siema({
            selector: '.carousel',
            duration: 200,
            easing: 'ease-in-out',
            perPage: 1,
            startIndex: 0,
            draggable: true,
            multipleDrag: false,
            threshold: 20,
            loop: true,
            rtl: false,
            onInit: () => {},
            onChange: () => {},
        });

        prev = () => {
            slider.prev()
            if (select > 0) {
                select--
            }
        }

        next = () => {
            slider.next()
            if (select > 0) {
                select++
            }
        }
    })

    const images = [
        { src: 'src/images/buses.png', description: 'bus' }
    ]
</script>

<head> <title>PN Travels • Home</title> </head>

<body>
    <div class="front-graphic">
        <div class="carousel">
            {#each images as d}
                <img class="slider" src={d.src} alt={d.description}>
            {/each}
        </div>
        <div class="graphic-nav">
            <img src="src/icons/chevron.svg" alt="<" class="chevron-left" on:click={prev}>
            <h1 class="graphic-text">Travel With Pride.</h1>
            <img src="src/icons/chevron.svg" alt=">" class="chevron-right" on:click={next}>
        </div>
    </div>

    <span class="headline">Unbeatable Pricing. Unmatchable Experience.<br>Unforgettable Memories.</span>

    <div class="article-container">
        <div><Article title="PN Travels" img='src/images/bus-img.jpg' content="Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet."/></div>
        <div><Article title="PN Travels" img='src/images/bus-img.jpg' content="Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet."/></div>
        <div><Article title="PN Travels" img='src/images/bus-img.jpg' content="Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet."/></div>
        <div><Article title="PN Travels" img='src/images/bus-img.jpg' content="Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet Lorem Ipsum Dolor Amet."/></div>
    </div>
</body>

<style lang="scss">
    :root {
        --eggshell: #E4E3D3;
        --cambridge-blue: #A9C1A2;
        --asparagus: #6D9F71;
        --dark-spring-green: #337357;
        --dark-slate-gray: #315052;
        --space-cadet: #2E2D4D;

        --muted-grey: #1F1F1F;
        --subtle-grey: #1F1F1FBF;
    }

    @font-face {
        font-family: 'DM Sans';
        src: url('../fonts/DMSans.ttf');
        font-style: normal;
    }

    @font-face {
        font-family: 'DM Sans';
        src: url('../fonts/DMSans-Italic.ttf');
        font-style: italic;
    }

    :global(*) {
        font-family: 'DM Sans', serif;
        font-size: 16px;
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }

    :global(body) {
        background-color: var(--eggshell);
        display: flex;
        flex-direction: column;
    }

    :global(::-webkit-scrollbar) {
        width: 0;
    }

    .front-graphic {
        margin-bottom: 2rem;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .front-graphic img {
        display: block;
        width: 100vw;
        user-select: none;
        mask-image: linear-gradient(to bottom, black 90%, transparent 100%);
        filter: saturate(150%);
    }

    .graphic-nav {
        width: 100vw;
        position: absolute;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
    }

    .chevron-left {
        width: 4rem;
        height: 4rem;
        rotate: 180deg;
    }

    .chevron-right {
        width: 4rem;
        height: 4rem;
    }

    .graphic-text {
        width: 1000rem;
        font-size: 8rem;
        color: var(--eggshell);
        font-weight: 900;
        user-select: none;
        text-align: center;
        text-shadow: 0 0 1rem var(--muted-grey);
    }

    .headline {
        margin: 4rem 0;
        background: linear-gradient(to right, var(--dark-slate-gray), var(--dark-spring-green) );
        color: var(--eggshell);
        text-align: center;
        font-size: 3rem;
        font-weight: 900;
    }

    .article-container {
        width: 100vw;
        height: max-content;
        display: flex;
        flex-direction: column;
    }

    .article-container div:nth-child(odd) {
        align-self: flex-start;
    }

    .article-container div:nth-child(even) {
        align-self: flex-end;
    }
</style>
