<script>
    import { onMount } from "svelte";

    const WIDTH = 70;
    const HEIGHT = 70;
    const OFFSET = 6;

    const topLeft = {
        x: OFFSET + 4,
        y: HEIGHT / 3 - 2,
    };
    const topCenter = {
        x: WIDTH / 3 + 6,
        y: HEIGHT / 3 - 2,
    };
    const topRight = {
        x: (WIDTH / 3) * 2 + 2,
        y: HEIGHT / 3 - 2,
    };
    const centerLeft = {
        x: OFFSET + 4,
        y: HEIGHT / 2 + 6,
    };
    const centerCenter = {
        x: WIDTH / 3 + 6,
        y: HEIGHT / 2 + 6,
    };
    const centerRight = {
        x: (WIDTH / 3) * 2 + 2,
        y: HEIGHT / 2 + 6,
    };
    const bottomLeft = {
        x: OFFSET + 4,
        y: HEIGHT - OFFSET - 2,
    };
    const bottomCenter = {
        x: WIDTH / 3 + 6,
        y: HEIGHT - OFFSET - 2,
    };
    const bottomRight = {
        x: (WIDTH / 3) * 2 + 2,
        y: HEIGHT - OFFSET - 2,
    };
    const positions = [
        topLeft,
        topCenter,
        topRight,
        centerLeft,
        centerCenter,
        centerRight,
        bottomLeft,
        bottomCenter,
        bottomRight,
    ];

    function drawGrid(ctx) {
        ctx.beginPath();
        ctx.moveTo(OFFSET, HEIGHT / 3 + 2);
        ctx.lineTo(WIDTH - OFFSET, HEIGHT / 3 + 2);
        ctx.stroke();

        ctx.beginPath();
        ctx.moveTo(OFFSET, (HEIGHT / 3) * 2 - 2);
        ctx.lineTo(WIDTH - OFFSET, (HEIGHT / 3) * 2 - 2);
        ctx.stroke();

        /* Draw two vertical lines */
        ctx.beginPath();
        ctx.moveTo(WIDTH / 3 + 2, OFFSET);
        ctx.lineTo(WIDTH / 3 + 2, HEIGHT - OFFSET);
        ctx.stroke();

        ctx.beginPath();
        ctx.moveTo((WIDTH / 3) * 2 - 2, OFFSET);
        ctx.lineTo((WIDTH / 3) * 2 - 2, HEIGHT - OFFSET);
        ctx.stroke();
    }

    var usedNumbers = [];
    var usedPositions = [];

    onMount(() => {
        var canvas = document.getElementById("sudoku");
        var ctx = canvas.getContext("2d");

        ctx.strokeStyle = "#eee";
        ctx.lineWidth = 1.5;

        drawGrid(ctx);

        ctx.font = "bold 17px Inter";
        ctx.fillStyle = "#ffffff";
        ctx.textAlign = "left";

        /* Dark magic */
        /* Determines how fast to draw new numbers */
        let test = 175;
        let update = 0;
        setInterval(() => {
            if (document.getElementById("sudoku-div").matches(":hover")) {
                update = 0;
            }
            if (update == 0) {
                updateBoard(positions, ctx);
                update = 2;
            } else {
                update--;
            }
        }, test);
    });

    function updateBoard(positions, ctx) {
        if (usedNumbers.length == 9) {
            usedNumbers = [];
            usedPositions = [];
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            drawGrid(ctx);
            return;
        }

        /* Randomly */
        let random1 = Math.floor(Math.random() * 9);
        let random2 = Math.floor(Math.random() * 9 + 1);
        while (usedPositions.includes(random1)) {
            random1 = Math.floor(Math.random() * 9);
        }
        while (usedNumbers.includes(random2)) {
            random2 = Math.floor(Math.random() * 9 + 1);
        }
        usedPositions.push(random1);
        usedNumbers.push(random2);
        ctx.fillText(random2, positions[random1].x, positions[random1].y);
    }
</script>

<div class="hoverable interactive-box" id="sudoku-div">
    <canvas id="sudoku" width="70px" height="70px" />
</div>

<style>
    .interactive-box {
        right: 150px;
        top: 120px;
        rotate: 9deg;
    }
    @media (max-width: 1100px) {
        .interactive-box {
            top: 60px;
        }
    }
    canvas {
        background-color: #0096ff;
    }
</style>
