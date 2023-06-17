<div class="hoverable interactive-box">
    <img src="/slibo_bg.png" alt="Slibotechny background" />
    <img src="/slibo_logo.png" alt="Slibotechny logo" id="abs" />
</div>

<style>
    .interactive-box {
        background-color: #f3f3f3;

        top: 120px;
        left: 20px;

        rotate: -7deg;
    }
    @media (max-width: 1000px) {
        .interactive-box {
            top: 50px;
        }
    }

    #abs {
        position: absolute;

        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);

        width: 40px;
        object-fit: contain;
    }
    .interactive-box:hover #abs {
        animation: jump 0.5s ease-in-out;
    }

    @keyframes jump {
        0% {
            top: 50%;
        }
        50% {
            top: 30%;
        }
        100% {
            top: 50%;
        }
    }

    img {
        height: 100%;
    }
</style>
