<script>
    import { onMount } from "svelte";

    export let path;
    export let alt;
    export let width = 100;
    export let description = "";

    let modal_div;
    let modalImage;

    function modal() {
        modal_div.style.display = "block";
    }
    function hideImage() {
        modal_div.style.display = "none";
    }

    let loaded = false;
    let thisImage;
    onMount(() => {
        thisImage.onload = () => {
            loaded = true;
        };
    });
</script>

<figure>
    <img
        src={path}
        {alt}
        class="image"
        style="width: {width}%;"
        on:click={() => {
            modal();
        }}
        bind:this={thisImage}
        loading="lazy"
    />
    {#if description != ""}
        <figcaption><i>{description}</i></figcaption>
    {/if}
</figure>

<div class="modal" bind:this={modal_div} on:click={hideImage}>
    <img loading="lazy" src={path} {alt} bind:this={modalImage} />
</div>

<style>
    figure {
        margin: 0;
    }
    figcaption {
        font-size: 16px;
        text-align: center;
        margin-top: 5px;
        margin-bottom: 40px;
        color: #6a6a6a;
    }
    .image {
        margin-top: 30px;
        margin-left: 50%;
        transform: translateX(-50%);
        border-radius: 12px;
        max-height: calc(100% - 100px);

        cursor: zoom-in;
        transition: 0.15s;
    }
    .image:hover {
        opacity: 0.85;
    }

    .modal {
        display: none; /* Hidden by default */
        position: fixed; /* Stay in place */
        z-index: 1; /* Sit on top */
        padding-top: 50px; /* Location of the box */
        left: 0;
        top: 0;
        width: 100%; /* Full width */
        height: 100%; /* Full height */
        background-color: rgb(0, 0, 0); /* Fallback color */
        background-color: rgba(0, 0, 0, 0.9); /* Black w/ opacity */
    }
    .modal img {
        margin: auto;
        display: block;
        border-radius: 12px;
        animation: show 0.1s ease-out;
        cursor: zoom-out;

        max-height: 90%;
        max-width: 90%;
    }
    @keyframes show {
        0% {
            transform: scale(0.8);
            filter: blur(25px);
        }
        100% {
            transform: scale(1);
            filter: blur(0);
        }
    }
</style>
