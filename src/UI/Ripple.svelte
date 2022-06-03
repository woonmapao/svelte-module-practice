<div>
    <div class="circle xxlarge shade1" />
    <div class="circle xlarge shade2" />
    <div class="circle large shade3" />
    <div class="circle medium shade4" />
    <div class="circle small shade5" />
</div>

<style>
    .circle {
        /* position: absolute; */
        position: fixed;
        border-radius: 50%;
        background: white;
        animation: ripple 15s infinite;
        box-shadow: 0px 0px 1px 0px #8cc0de;
        z-index: -1;
    }

    .small {
        width: 200px;
        height: 200px;
        left: -100px;
        bottom: 50%;
    }

    .medium {
        width: 400px;
        height: 400px;
        left: -200px;
        bottom: 50%;
    }

    .large {
        width: 600px;
        height: 600px;
        left: -300px;
        bottom: 50%;
    }

    .xlarge {
        width: 800px;
        height: 800px;
        left: -400px;
        bottom: 50%;
    }

    .xxlarge {
        width: 1000px;
        height: 1000px;
        left: -500px;
        bottom: 50%;
    }

    .shade1 {
        opacity: 0.2;
    }
    .shade2 {
        opacity: 0.5;
    }
    .shade3 {
        opacity: 0.7;
    }
    .shade4 {
        opacity: 0.8;
    }
    .shade5 {
        opacity: 0.9;
    }

    @keyframes ripple {
        0% {
            transform: scale(0.8);
        }

        50% {
            transform: scale(1.2);
        }

        100% {
            transform: scale(0.8);
        }
    }
</style>
