<div class="hoverable interactive-box">
    <img src="/jack.png" alt="Card Jack of Hearths" />
</div>

<style>
    .interactive-box {
        left: 50%;
        top: 70px;

        background-color: #ff2959;

        rotate: -5deg;
    }

    @media (max-width: 1100px) {
        .interactive-box {
            top: 40px;
        }
    }

    img {
        height: 80%;

        box-shadow: 2px 2px 10px 0px rgba(0, 0, 0, 0.45);

        animation: slide-in-out 2.5s infinite;
    }

    @keyframes slide-in-out {
        0% {
            transform: translateX(-100px) translateY(-7px);
            rotate: -1deg;
        }
        14% {
            rotate: 0deg;
        }
        32% {
            transform: translateX(0px);
            rotate: 7deg;
        }
        68% {
            transform: translateX(0px);
            rotate: 7deg;
        }
        100% {
            transform: translateX(100px) translateY(2px);
        }
    }
</style>
