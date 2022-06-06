<script>
    import Button from "../UI/Button.svelte";
    import { createEventDispatcher } from "svelte";
    import Badge from "../UI/Badge.svelte";

    export let id;
    export let title;
    export let subtitle;
    export let imageUrl;
    export let description;
    export let address;
    export let email;
    export let isFav;

    const dispatch = createEventDispatcher();
</script>

<article>
    <header>
        <h1>
            {title}
            {#if isFav}
                <Badge>FAVOURITE</Badge>
            {/if}
        </h1>
        <h2>{subtitle}</h2>
        <p>{address}</p>
    </header>
    <div>
        <img src={imageUrl} alt={title} class="image" />
    </div>
    <div class="content">
        <p>{description}</p>
    </div>
    <footer>
        <Button href="mailto:{email}">Contact</Button>
        <Button
            mode="outline"
            color={isFav ? null : "success"}
            type="button"
            on:click={() => dispatch("toggle-favourite", id)}
            >{isFav ? "Unfavourite" : "Favourite"}</Button
        >
        <Button type="button">Show Details</Button>
    </footer>
</article>

<style>
    article {
        box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
        border-radius: 5px;
        background: white;
        margin: 1rem;
    }

    header,
    .content,
    footer {
        padding: 1rem;
    }

    .image {
        width: 100%;
        height: 14rem;
    }

    h1 {
        font-size: 1.25rem;
        margin: 0.5rem 0;
        font-family: "Roboto Slab", sans-serif;
    }

    h2 {
        font-size: 1rem;
        color: #808080;
        margin: 0.5rem 0;
    }

    p {
        font-size: 1.25rem;
        margin: 0;
    }

    div {
        text-align: right;
    }

    img {
        width: 100%;
        height: 80%;
    }
</style>
