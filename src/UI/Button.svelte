<script>
    export let type = "button";
    export let href = null;
    export let mode = null;
    export let color = null;
</script>

{#if href}
    <a {href}><slot /></a>
{:else}
    <button class="{mode} {color}" {type} on:click><slot /></button>
{/if}

<style>
    button,
    a {
        font: inherit;
        border: 1px solid #99ddcc;
        background: #99ddcc;
        padding: 0.5rem 1rem;
        color: white;
        border-radius: 5px;
        box-shadow: 1px 1px 3px rgba(0, 0, 0, 0.26);
        cursor: pointer;
        text-decoration: none;
    }

    button:focus {
        outline: none;
    }

    button:hover,
    button:active,
    a:hover,
    a:active {
        background: #ffe2e2;
        border-color: #ffe2e2;
        box-shadow: 1px 1px 8px rgba(77, 51, 51, 0.26);
    }

    button:disabled,
    button:disabled:hover,
    button:disabled:active {
        background: #ccc;
        border-color: #ccc;
        color: #959595;
        box-shadow: none;
        cursor: not-allowed;
    }

    .success {
        background: #01a129;
        border-color: #01a129;
    }

    .success:hover,
    .success:active {
        background: #1ac745;
        border-color: #1ac745;
    }

    .outline {
        background: transparent;
        color: #99ddcc;
        box-shadow: none;
    }

    .outline:hover,
    .outline:active {
        background: #ff6e6e;
        box-shadow: none;
        color: #ccc;
    }

    .outline:disabled,
    .outline:disabled:hover,
    .outline:disabled:active {
        background: transparent;
        color: #ccc;
    }

    .outline.success {
        border-color: #99ddcc;
        color: #99ddcc;
    }

    .outline.success:hover,
    .outline.success:active {
        border-color: #ffc7de;
        color: #fff;
        background: #ffc7de;
    }
</style>
