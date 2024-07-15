<script>
    export let title = 'Title';
    export let img = 'src/images/bus-img.jpg';
    export let content = 'Lorem Ipsum Dolor Amet.';
</script>

<article class="article">
    <img src={img} alt="img" class="article-img">
    <div class="article-content">
        <h1 class="article-header">{title}</h1>
        <p class="article-paragraph">{@html content}</p>
    </div>
</article>

<style>
    .article {
        margin: 2rem;
        padding: 0.5rem;
        width: 48rem;
        height: 24rem;
        background: var(--dark-slate-gray);
        border-radius: 1rem;
        display: flex;
        flex-direction: row;
        align-items: center;
        box-shadow: 0 0 1rem var(--space-cadet);
    }

    .article-img {
        width: 23rem;
        height: 23rem;
        border-radius: 0.5rem;
    }

    .article-content {
        margin: 0.5rem 0.5rem 0.5rem 1rem;
        height: 23rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;
    }

    .article-header {
        padding-bottom: 2rem;
        width: fit-content;
        font-size: 2rem;
        font-weight: 700;
        text-align: center;
        color: var(--cambridge-blue);
        filter: drop-shadow(0 0 0.5rem var(--muted-grey));
    }

    .article-paragraph {
        font-weight: 500;
        color: var(--eggshell);
        text-align: justify;
    }
</style>
