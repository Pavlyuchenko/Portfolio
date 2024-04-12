<script>
    import { onMount } from "svelte";

    const WIDTH = 70;
    const HEIGHT = 70;
    const OFFSET = 5;

    let iterationNumber = -1;

    let textFirst = ["Hello!", "DON'T!"];
    let textSecond = ["this is a", "HOVER"];
    let textThird = ["text editor", "OVER ME!"];
    let hovering = 0;

    onMount(() => {
        var canvas = document.getElementById("text-ed");
        var ctx = canvas.getContext("2d");

        setInterval(() => {
            ctx.clearRect(0, 0, WIDTH, HEIGHT);

            if (document.getElementById("text-ed-div").matches(":hover")) {
                hovering = 1;
            } else {
                hovering = 0;
            }

            ctx.font = "bold 18px Inter";
            ctx.fillStyle = "#ffffff";
            ctx.textAlign = "left";
            ctx.textBaseline = "top";
            ctx.fillText(
                textFirst[hovering].substring(0, iterationNumber),
                OFFSET,
                OFFSET + 2
            );

            ctx.font = "bold 12px Inter";
            ctx.fillText(
                textSecond[hovering].substring(
                    0,
                    iterationNumber - textFirst[hovering].length
                ),
                OFFSET,
                30
            );
            ctx.fillText(
                textThird[hovering].substring(
                    0,
                    iterationNumber -
                        textFirst[hovering].length -
                        textSecond[hovering].length
                ),
                OFFSET,
                45
            );

            if (
                iterationNumber -
                    textFirst[hovering].length -
                    textSecond[hovering].length -
                    textThird[hovering].length >
                10
            )
                iterationNumber = -1;

            iterationNumber++;
        }, 116);
    });
</script>

<div class="hoverable interactive-box" id="text-ed-div">
    <canvas id="text-ed" width="70px" height="70px" />
</div>

<style>
    .interactive-box {
        right: 45px;
        top: 250px;

        rotate: -10deg;
    }
    @media (max-width: 1100px) {
        .interactive-box {
            top: 300px;
        }
    }
    canvas {
        background-color: #ff8a00;
    }
</style>
