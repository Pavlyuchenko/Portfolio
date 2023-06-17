<div class="hoverable interactive-box">
    <div id="cube" />
    <img src="/ChatBotFight.png" alt="ChatBotFight Logo" />
</div>

<style>
    .interactive-box {
        background-color: #f3f3f3;
        border: 2px solid #444;

        display: flex;
        flex-direction: column;

        left: 40%;
        top: 580px;

        rotate: -7deg;
    }

    @media (max-width: 1100px) {
        .interactive-box {
            top: 400px;
        }
    }

    .interactive-box:hover #cube {
        animation: jump 0.55s;
    }

    @keyframes jump {
        0% {
            transform: translateY(0px) rotate(0deg);
        }
        50% {
            transform: translateY(-10px) rotate(45deg) scale(1.1);
        }
        100% {
            transform: translateY(0px) rotate(90deg);
        }
    }

    #cube {
        width: 10px;
        height: 10px;
        background-color: #4285f4;
    }

    img {
        height: 60%;
    }
</style>
