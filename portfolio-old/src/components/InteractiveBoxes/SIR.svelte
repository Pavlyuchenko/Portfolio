<script>
    import { onMount } from "svelte";

    const WIDTH = 70;
    const HEIGHT = 70;
    const BORDER = 6 + 4;

    const HEALTHY = "#29B6F6";
    const INFECTED = "#FF4F4F";
    const RECOVERED = "#616161";

    const STARTING_POSITIONS = [
        { x: 16, y: 15, starting: HEALTHY },
        { x: 54, y: 50, starting: HEALTHY },
        { x: 42, y: 11, starting: INFECTED },
        { x: 12, y: 42, starting: INFECTED },
        { x: 20, y: 56, starting: RECOVERED },
        { x: 40, y: 35, starting: RECOVERED },
    ];

    class Person {
        constructor(x, y, color) {
            this.x = x;
            this.y = y;
            this.color = color;
            this.hovered = false;

            /* velocity random between -0.4 and -0.2 or 0.2 and 0.4 */
            this.velX =
                (Math.random() * 0.2 + 0.25) * (Math.random() < 0.5 ? -1 : 1);
            this.velY =
                (Math.random() * 0.2 + 0.25) * (Math.random() < 0.5 ? -1 : 1);
        }

        draw(ctx) {
            ctx.beginPath();
            ctx.arc(this.x, this.y, 6, 0, 2 * Math.PI);
            ctx.fillStyle = this.color;
            ctx.fill();
        }

        update() {
            if (this.x < BORDER || this.x > WIDTH - BORDER) {
                this.velX *= -1;
            }
            if (this.y < BORDER || this.y > HEIGHT - BORDER) {
                this.velY *= -1;
            }

            if (this.hovered) {
                this.x += this.velX * 2.25;
                this.y += this.velY * 2.25;
                return;
            }

            this.x += this.velX;
            this.y += this.velY;
        }
    }

    onMount(() => {
        var canvas = document.getElementById("canvas");
        var ctx = canvas.getContext("2d");

        var people = [];

        for (var i = 0; i < STARTING_POSITIONS.length; i++) {
            var pos = STARTING_POSITIONS[i];
            people.push(new Person(pos.x, pos.y, pos.starting));
        }

        for (var i = 0; i < people.length; i++) {
            people[i].draw(ctx);
        }

        setInterval(() => {
            ctx.clearRect(0, 0, WIDTH, HEIGHT);

            let beingHovered = document
                .getElementById("sir-div")
                .matches(":hover");

            for (var i = 0; i < people.length; i++) {
                if (beingHovered) {
                    people[i].hovered = true;
                } else {
                    people[i].hovered = false;
                }
                people[i].update();
                people[i].draw(ctx);
            }
        }, 1000 / 60);
    });
</script>

<div class="hoverable interactive-box" id="sir-div">
    <canvas id="canvas" width="70px" height="70px" />
</div>

<style>
    .interactive-box {
        right: 100px;
        top: 500px;

        rotate: 6deg;
    }
    @media (max-width: 1100px) {
        .interactive-box {
            top: 450px;
        }
    }
    canvas {
        background-color: #303030;
    }
</style>
