<script>
    import Heading1 from "../../components/Heading1.svelte";
    import TextBlock from "../../components/TextBlock.svelte";
    import ImageLoader from "../../components/ImageLoader.svelte";
</script>

<svelte:head>
    <title>Upwork | Michal Pavlíček</title>
</svelte:head>

<article>
    <div>
        <div>
            <p id="date">aug. 2022 - now</p>
            <h1>Freelance Web Developer on Upwork</h1>
            <p id="description">
                I developer 5 projects for 4 clients recieving only 5 star
                ratings.
            </p>
        </div>
        <div id="image">
            <img loading="lazy" src="upwork_banner.webp" alt="Expobank logo" />

            <div id="project-info">
                <div>
                    <p class="project-info-title">My role</p>
                    <p class="project-info-value" id="role">Web Developer</p>
                </div>
                <div>
                    <p class="project-info-title">Technologies</p>
                    <p class="project-info-value" id="tech">
                        <img
                            src="js.png"
                            alt="Javascript logo"
                            title="Javascript"
                        />
                        <img
                            loading="lazy"
                            src="react.png"
                            alt="React logo"
                            title="React"
                        />
                        <img
                            loading="lazy"
                            src="html.svg"
                            alt="HTML logo"
                            title="HTML"
                        />
                    </p>
                </div>
                <div>
                    <p class="project-info-title">Interval</p>
                    <p class="project-info-value" id="interval">2+ months</p>
                </div>
            </div>
        </div>
    </div>

    <div id="the-story">
        <h3 class="epilogue">Lessons learned</h3>
        <div class="flex" id="epilogue-div">
            <div class="flex-child-left">
                <div class="lesson-title">Communication is key</div>
                <p>
                    For the first time I found myself having to talk to 4 native
                    English speakers on Zoom. Sounded daunting to me at first,
                    but suddenly I realized I was the one talking the most
                    anyways. That was a huge turning point for me, giving me the
                    confidence to speak up.
                </p>
            </div>
            <div class="flex-child-right">
                <div class="lesson-title">It's tough between projects</div>
                <p>
                    I also got the opportunity to witness the bad part of
                    freelancing, which is getting the clients in the first
                    place. When finishing one project, it can take quite a long
                    time to find a perfect match and is frustrating, when noone
                    responds to your proposals.
                </p>
            </div>
        </div>

        <h3>Prolog</h3>
        <p>
            I've been hearing about this freelance thing for a long time. It
            sounded like a dream to me, too good to be true, but I gave it a
            shot anyways. I had all the required skills and projects to prove
            them, so I registered and landed my first project within the first
            week. After that, empowered with my success, I managed to get 4
            more.
        </p>

        <Heading1
            description="Javascript Tree Algorithm"
            heading="My first Upwork project"
        />
        <TextBlock
            text="My first gig was for a client, who I guess needed his homework done. My task was to create an interactive knowledge tree with the ability to view it in levels and going one level up as well. So I had to code up an algorithm to to find node's children, parents and siblings, which deepened my knowledge in this area."
        />
        <ImageLoader path="/upwork_tree.png" alt="Upwork Tree" />
        <a
            href="https://pavlyuchenko.github.io/UpworkFirstProject/"
            target="_blank"
            style="font-size: 20px; font-weight: 700;">Demo</a
        >

        <Heading1
            description="Interactive Card Game"
            heading="My biggest client"
        />
        <TextBlock
            text="Skipping a few projects, I got the chance to create a HTML & JS card game for another client. This was probably my favorite project on Upwork so far, since it involved, well, creating a game. I used my OOP knowledge, as well as CSS animations, optimization and a lot more."
        />
        <ImageLoader path="/waterfall.png" alt="Waterfall Game" />
        <a
            href="https://pavlyuchenko.github.io/WaterfallGame/"
            target="_blank"
            style="font-size: 20px; font-weight: 700;">Demo</a
        >

        <Heading1
            description="My current project"
            heading="Recreating mobile app on the web"
        />
        <TextBlock
            text="Since we both enjoyed working with each other, the client from the card game recruited me for another project he was just working on. I was responsible for creating the visual side of things and connecting to an API. The aim of this project is making your pets talk using machine learning."
        />
        <ImageLoader path="/ticklefluff_img.png" alt="Ticklefluff" />
        <a
            href="https://dev.ticklefluff.com"
            target="_blank"
            style="font-size: 20px; font-weight: 700;">Demo</a
        >

        <h3 class="epilogue">Epilogue</h3>
        <div class="flex" id="epilogue-div">
            <p>
                I am grateful for starting my freelance journey on Upwork.
                Thanks to that I was able to afford living in the expensive
                Netherlands and study the Data Science & AI bachelor for a year
                Apart from that I learnt quite a lot of lessons talking to
                clients.
            </p>
        </div>
    </div>
</article>

<style>
    article {
        padding: 0px calc((100% - 60rem) / 2) 0px calc((100% - 60rem) / 2);

        margin-top: 40px;
    }
    article #date {
        font-size: 17px;
    }
    article h1 {
        font-family: "Inter";
        font-size: 36px;
        color: var(--primary);
    }

    #image {
        margin-top: 40px;
    }
    #image img {
        width: 100%;
    }
    #image #project-info {
        display: flex;
        justify-content: space-evenly;
        align-items: center;

        height: 150px;
        border: 1px solid var(--primary);
        margin-top: -10px;
        border-radius: 0 0 7px 7px;
    }
    #image p {
        text-align: center;
    }
    #image .project-info-title {
        font-weight: 500;
        font-size: 18px;
        position: relative;
    }
    #image .project-info-value {
        color: #6a6a6a;
        margin-top: 22px;
    }

    #image .project-info-title:after {
        position: absolute;
        content: "";
        height: 3px;
        bottom: -8px;

        margin: 0 auto;
        left: 0;
        right: 0;
        width: 30px;
        background: var(--secondary);
    }

    #project-info #tech {
        display: flex;
        justify-content: space-evenly;
    }
    #project-info img:nth-child(1) {
        width: 20px;
        height: 20px;
    }
    #project-info img:nth-child(2) {
        width: 17px;
        height: 20px;
    }
    #project-info img:nth-child(3) {
        width: 14px;
        height: 20px;
    }

    #the-story {
        margin-top: 80px;
    }
    #the-story h3 {
        font-family: "Inter";
        font-weight: 500;
        font-size: 30px;
        position: relative;

        color: var(--primary);
    }
    #the-story h3:after {
        position: absolute;
        content: "";
        height: 3px;
        bottom: -8px;

        left: 0;
        width: 30px;
        background: var(--secondary);
    }
    #the-story p {
        color: #6a6a6a;
        margin-top: 30px;
        margin-bottom: 30px;
        font-size: 20px;
        line-height: 30px;
    }

    .flex {
        display: flex;
    }
    .flex .flex-child-left {
        padding-right: 15px;
        width: 50%;
    }
    .flex .flex-child-right {
        padding-left: 15px;
        width: 50%;
    }
    hr {
        border-top: 1px solid var(--secondary);
        margin-top: 50px;
        margin-bottom: 50px;
    }

    .epilogue {
        margin-top: 60px;
        margin-bottom: 30px;
    }

    #epilogue-div {
        padding: 10px 15px;
        margin-bottom: 40px;

        background-color: var(--primary);
        border-radius: 7px;
    }

    #epilogue-div p {
        margin-top: 10px;

        color: #fff;
    }

    .flex .lesson-title {
        background-color: #fff;
        width: -moz-fit-content;
        width: fit-content;
        padding: 10px 18px;

        font-weight: 700;
        font-size: 18px;
    }

    @media (max-width: 700px) {
        .flex {
            flex-direction: column;
        }
        .flex .flex-child-left {
            padding-right: 0;
            width: 100%;
        }
        .flex .flex-child-right {
            padding-left: 0;
            width: 100%;
        }
    }
</style>
