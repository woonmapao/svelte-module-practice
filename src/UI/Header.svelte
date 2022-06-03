<header>
    <h1 class="tracking-in-contract">MeetMon</h1>
</header>

<style>
    header {
        position: fixed;
        width: 100%;
        top: 0;
        left: 0;
        height: 4rem;
        background: #f6f6f6;
        display: flex;
        justify-content: center;
        align-items: center;
        box-shadow: 0 2px 6px rgba(0, 0, 0, 0.26);
    }

    h1 {
        color: #99ddcc;
        font-family: "Roboto", sans-serif;
        margin: 0;
    }

    .tracking-in-contract {
        animation: tracking-in-contract 0.8s cubic-bezier(0.215, 0.61, 0.355, 1)
            0.8s both;
    }

    @keyframes tracking-in-contract {
        0% {
            letter-spacing: 1em;
            opacity: 0;
        }
        40% {
            opacity: 0.6;
        }
        100% {
            letter-spacing: normal;
            opacity: 1;
        }
    }
</style>
