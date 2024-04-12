<script>
    import { onMount } from "svelte";
    import Sir from "../components/InteractiveBoxes/SIR.svelte";
    import Waterfall from "../components/InteractiveBoxes/Waterfall.svelte";
    import GenSim from "../components/InteractiveBoxes/GenSim.svelte";
    import Sudoku from "../components/InteractiveBoxes/Sudoku.svelte";
    import TexEd from "../components/InteractiveBoxes/TexEd.svelte";
    import ChatBot from "../components/InteractiveBoxes/ChatBot.svelte";
    import Slibotechny from "../components/InteractiveBoxes/Slibotechny.svelte";

    const LOWER_TIME_DELETE_BOUND = 20;
    const UPPER_TIME_DELETE_BOUND = 45;
    const WAIT_TEXT_INTERVAL = 1800;

    let height;
    onMount(() => {
        height = document.getElementById("intro").offsetHeight + 60;
        document.getElementById("intro").style.height = height + 60 + "px";

        cursorFlicker();

        setTimeout(() => {
            deleteLetter();
        }, WAIT_TEXT_INTERVAL);

        /* setTimeout(() => {
			if (document.getElementById("country").innerHTML != "Czechia") {
				foreigner = true;
			}
		}, 500); */
    });

    function deleteLetter() {
        setTimeout(() => {
            variableText = variableText.slice(0, -1);

            if (variableText.length != 0) {
                cursor.style.color = "#2F3C7E";
                deleteLetter();
            } else {
                textOptionsIndex += 1;
                if (textOptionsIndex == textOptions.length) {
                    textOptionsIndex = 0;
                }

                addLetter();
            }
        }, Math.random() * UPPER_TIME_DELETE_BOUND + LOWER_TIME_DELETE_BOUND);
    }
    function addLetter() {
        setTimeout(() => {
            variableText =
                variableText + textOptions[textOptionsIndex][textIndex];

            if (
                variableText.length <=
                textOptions[textOptionsIndex].length - 1
            ) {
                textIndex += 1;
                cursor.style.color = "#2F3C7E";
                addLetter();
            } else {
                cursorFlicker();
                textIndex = 0;

                setTimeout(() => {
                    cursor.style.color = "#2F3C7E";
                    deleteLetter();
                }, WAIT_TEXT_INTERVAL);
            }
        }, Math.random() * UPPER_TIME_DELETE_BOUND + LOWER_TIME_DELETE_BOUND);
    }
    function cursorFlicker() {
        let cursorIsOn = true;
        let inter = setInterval(() => {
            if (cursorIsOn) {
                cursorIsOn = false;
                cursor.style.color = "transparent";
            } else {
                cursorIsOn = true;
                cursor.style.color = "#2F3C7E";
            }
        }, WAIT_TEXT_INTERVAL / 4);

        setTimeout(() => {
            clearInterval(inter);
        }, WAIT_TEXT_INTERVAL);
    }

    let textOptionsIndex = 0;
    let textIndex = 0;
    let textOptions = [
        "I am a programmer",
        "you can click any of the boxes around!",
        "I am a full-stack developer",
        "I know Python, Javascript and Java",
        "I'm moving to Brno, Czechia",
        "the meaning of life is 42",
        "I speak English, Czech und ein bisschen Deutsch",
        "I studied in Maastricht, Netherlands",
    ];

    let variableText = textOptions[textOptionsIndex];
    let cursor;
</script>

<div id="main-div">
    <div id="intro">
        <h1>
            My name is Michal and <br />
            <span id="changing-text">
                {variableText}<span bind:this={cursor} id="cursor">|</span>
            </span>
        </h1>

        <div id="interactive-boxes">
            <a href="https://www.slibotechny.cz/" target="_blank">
                <Slibotechny />
            </a>
            <a
                href="https://pavlyuchenko.github.io/WaterfallGame"
                target="_blank"
            >
                <Waterfall />
            </a>
            <a href="https://pavlyuchenko.github.io/Sudoku" target="_blank">
                <Sudoku />
            </a>
            <a href="/showcase/text-editor" target="_blank">
                <TexEd />
            </a>
            <a href="https://generationsimulation.com/" target="_blank">
                <GenSim />
            </a>
            <a href="https://www.chatbotfight.com/" target="_blank">
                <ChatBot />
            </a>
            <a href="https://pavlyuchenko.github.io/SIRModel" target="_blank">
                <Sir />
            </a>
        </div>
    </div>

    <p id="my-work_2">Experience</p>
    <hr />

    <div id="projects">
        <a href="/project/upwork">
            <article id="upwork">
                <div class="project-info">
                    <img
                        src="upwork_logo.png"
                        alt="Upwork logo"
                        width="45"
                        height="45"
                    />
                    <div>
                        <p class="project-date">aug. 2022 - now</p>
                        <h2 class="project-name">Freelance Web Developer</h2>
                        <p class="project-description">
                            Started my freelance journey on Upwork and created
                            projects for 4 clients so far.
                        </p>
                        <p class="project-tag">Work</p>
                    </div>
                </div>
                <img id="image" src="ticklefluff.png" alt="Ticklefluff" />
            </article>
        </a>
        <a href="/project/expobank">
            <article id="expobank">
                <div class="project-info">
                    <img
                        src="expo_logo.png"
                        alt="Expobank logo"
                        width="45"
                        height="45"
                    />
                    <div>
                        <p class="project-date">jan. 2022 - mar. 2022</p>
                        <h2 class="project-name">Testing Expobank</h2>
                        <p class="project-description">
                            I was given the task of testing existing website of
                            one of the most well-known banks in the Czech
                            Republic.
                        </p>
                        <p class="project-tag">Testing</p>
                    </div>
                </div>
            </article>
        </a>
        <a href="/project/partners">
            <article id="partners">
                <div class="project-info">
                    <img
                        src="partners.png"
                        alt="Partners logo"
                        width="45"
                        height="45"
                    />
                    <div>
                        <p class="project-date">sep. 2021 - dec. 2021</p>
                        <h2 class="project-name">Partners execution</h2>
                        <p class="project-description">
                            During my first professional experience I've worked
                            on a project for a company doing financal advisory.
                        </p>
                        <p class="project-tag">Work</p>
                    </div>
                </div>
                <img
                    id="image"
                    src="partners_main.png"
                    alt="Obrázek Slibotechny"
                />
            </article>
        </a>
        <a href="/project/velka-domu">
            <article id="velka-domu">
                <div class="project-info">
                    <img
                        loading="lazy"
                        src="velkadomu.png"
                        alt="VelkáDomů.cz logo"
                    />
                    <div>
                        <p class="project-date">nov. 2020 - feb. 2021</p>
                        <h2 class="project-name">VelkáDomů.cz</h2>
                        <p class="project-description">
                            I've created a whole football portal together with a
                            CMS and a block based text editor.
                        </p>
                        <p class="project-tag">Group project</p>
                    </div>
                </div>
                <img
                    id="image"
                    src="https://ik.imagekit.io/velkadomu/velkadomu_image_IQaeE2EQC.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504371549"
                    alt="Obrázek VelkáDomů.cz"
                />
            </article>
        </a>
        <a href="/project/slibotechny">
            <article id="slibotechny">
                <div class="project-info">
                    <img loading="lazy" src="qm.png" alt="Slibotechny logo" />
                    <div>
                        <p class="project-date">aug. 2021 - dec. 2021</p>
                        <h2 class="project-name">Slibotechny</h2>
                        <p class="project-description">
                            Project focusing on controlling the promises of
                            political parties.
                        </p>
                        <p class="project-tag">Group project</p>
                    </div>
                </div>
                <img
                    id="image"
                    src="https://ik.imagekit.io/velkadomu/slibotechny_sliced_NY1siBbbWn.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504369511"
                    alt="Obrázek Slibotechny"
                />
            </article>
        </a>
        <a href="/project/vanocni-florbalovy-turnaj">
            <article id="vfb">
                <div class="project-info">
                    <img
                        loading="lazy"
                        src="vft.png"
                        alt="Vánoční florbalový turnaj logo"
                    />
                    <div>
                        <p class="project-date">may. 2020 - jun. 2020</p>
                        <h2 class="project-name">
                            Unihockey School Tournament
                        </h2>
                        <p class="project-description">
                            Web application intended for the real-time control
                            of matches.
                        </p>
                        <p class="project-tag">Project</p>
                    </div>
                </div>
                <img
                    id="image"
                    src="https://ik.imagekit.io/velkadomu/vfb_image_5DHuL1Jzw.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504349279"
                    alt="Obrázek VelkáDomů.cz"
                />
            </article>
        </a>
        <a href="/project/sir-model">
            <article id="sir">
                <div class="project-info">
                    <img loading="lazy" src="sir.png" alt="SIR logo" />
                    <div>
                        <p class="project-date">may. 2020</p>
                        <h2 class="project-name">SIR Model</h2>
                        <p class="project-description">
                            I programmed an animation of the simplest epidemic
                            model.
                        </p>
                        <p class="project-tag">Projekt</p>
                    </div>
                </div>
                <img
                    id="image"
                    src="https://ik.imagekit.io/velkadomu/sir_image_Yfk3BJb7a.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504368171"
                    alt="Obrázek VelkáDomů.cz"
                />
            </article>
        </a>
        <a href="/project/projekt-jidelna">
            <article id="pj">
                <div class="project-info">
                    <img
                        loading="lazy"
                        src="pj.png"
                        alt="Projekt Jídelna logo"
                    />
                    <div>
                        <p class="project-date">apr. 2019 - jul. 2019</p>
                        <h2 class="project-name">Projekt Canteen</h2>
                        <p class="project-description">
                            I created a website, whose purpose is to simplify
                            the choice of meals in school canteen.
                        </p>
                        <p class="project-tag">Group project</p>
                    </div>
                </div>
                <img
                    loading="lazy"
                    id="image"
                    src="https://ik.imagekit.io/velkadomu/pj_image_Qr3nNIE-W.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504362601"
                    alt="Obrázek VelkáDomů.cz"
                />
            </article>
        </a>
    </div>
</div>

<style>
    :global(canvas) {
        width: 70px;
        height: 70px;

        border-radius: 10px;
    }
    :global(.hoverable) {
        transition: 0.2s ease-in-out;
    }
    :global(.hoverable:hover) {
        cursor: pointer;
        transform: scale(1.15);
        box-shadow: 2px 2px 10px 0px rgba(0, 0, 0, 0.5);
    }
    :global(.interactive-box) {
        position: absolute;

        width: 70px;
        height: 70px;
        border-radius: 10px;

        display: flex;
        justify-content: center;
        align-items: center;

        overflow: hidden;
    }
    #interactive-boxes {
        position: absolute;

        top: 0px;
        left: max(calc((100% - 73rem) / 2), 0px);
        right: max(calc((100% - 73rem) / 2), 0px);

        box-sizing: border-box;
    }

    #main-div {
        padding: 0px calc((100% - 73rem) / 2) 0px calc((100% - 73rem) / 2);

        position: relative;

        padding-top: 250px;
    }

    #intro {
        display: flex;

        width: 100%;
        justify-content: center;
    }

    h1 {
        text-align: center;

        color: var(--primary);
        font-weight: 700;
        font-family: "Inter", sans-serif;
        font-size: 64px;
        line-height: 67px;

        margin-top: 20px;
    }
    #changing-text {
        color: var(--secondary);
    }
    #cursor {
        color: var(--primary);
    }

    #my-work_2 {
        margin-top: 180px;
        font-family: "Inter";
        margin-bottom: 0px;
        font-weight: 500;
        color: var(--primary);
    }
    hr {
        border-top: 2px solid var(--primary);
        margin-bottom: 40px;
    }

    #projects {
        display: grid;
        gap: 20px;
        grid-template-columns: minmax(0, 1fr) minmax(0, 1fr);
        grid-template-rows: 1fr;
    }
    #projects article {
        width: 100%;
        min-height: 280px;

        padding: 25px 35px;
        padding-right: 0;

        border-radius: 4px;

        display: flex;
        align-items: center;

        cursor: pointer;
        transition: 0.25s cubic-bezier(0, 0, 0.4, 1);
        box-sizing: border-box;
    }
    #projects a {
        text-decoration: none;
    }
    #projects article:hover {
        transform: scale(1.05);
        box-shadow: 4px 4px 18px 8px rgba(33, 33, 33, 0.25);
    }
    .project-info {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: flex-start;

        height: 100%;
        flex: 100;
    }
    .project-name {
        font-family: "Inter";
        font-weight: 600;
        color: #ffffff;
        font-size: 26px;
    }

    #projects article #image {
        object-fit: cover;
        width: 100%;
        flex: 1;
        max-height: 290px;
    }

    .project-tag {
        font-weight: 500;
        margin-bottom: 10px;
        font-size: 18px;
    }
    .project-date {
        font-weight: 500;
        margin-bottom: 10px;
        font-size: 15px;
    }
    #velka-domu .project-description {
        font-size: 15px;
        line-height: 130%;
    }

    #upwork {
        background-color: #00aa00;
        color: #fff;
    }
    #expobank {
        background-color: #00465a;
        color: #fff;
        font-weight: 500;
        height: 100%;
    }
    #expobank .project-name {
        color: #fff;
        font-weight: 700;
    }
    #expobank .project-date {
        color: #ccc;
    }
    #expobank .project-tag {
        color: #ccc;
    }
    #partners {
        background: url("/partners_bg.png");
        font-weight: 500;
    }
    #partners .project-name {
        color: #009fb5;
        font-weight: 700;
    }
    #slibotechny {
        background: url("/slibotechny.png");
        font-weight: 500;
    }
    #slibotechny .project-name {
        color: #000000;
        font-weight: 700;
    }

    #velka-domu {
        background-color: #ff8a00;
    }
    #velka-domu .project-date {
        color: #515151;
    }
    #velka-domu .project-tag {
        color: #515151;
    }
    #velka-domu .project-description {
        color: #ffffff;
    }

    #vfb {
        background-color: #e63946;
    }
    #vfb .project-date {
        color: #722d32;
    }
    #vfb .project-tag {
        color: #722d32;
    }
    #vfb .project-description {
        color: #ffffff;
    }

    #sir {
        background-color: #303030;
    }
    #sir .project-date {
        color: #c7c7c7;
    }
    #sir .project-tag {
        color: #c7c7c7;
    }
    #sir .project-description {
        color: #ffffff;
    }

    #pj {
        background-color: #19a7d8;
    }
    #pj .project-date {
        color: #515151;
    }
    #pj .project-tag {
        color: #515151;
    }
    #pj .project-description {
        color: #ffffff;
    }

    @media (max-width: 1100px) {
        h1 {
            margin-top: 0px;
        }
        #main-div {
            padding-left: 0px;
        }
        #projects {
            grid-template-columns: minmax(0, 1fr);
        }
        #projects a {
            width: 100%;
        }

        #projects article {
            padding-right: 0;
            position: relative;
        }
        #projects article #image {
            max-width: 300px;
        }
        #main-div {
            padding-top: 100px;
        }
    }
    @media (max-width: 900px) {
        #interactive-boxes {
            position: relative;
            width: 100%;

            display: grid;
            grid-template-rows: 1fr 1fr;
            grid-template-columns: 1fr 1fr 1fr 1fr;
            gap: 20px;
            justify-content: center;

            margin-top: 60px;
        }
        #intro {
            display: flex;
            flex-direction: column;
        }
        :global(.interactive-box) {
            position: relative;
            top: 0 !important;
            left: 0 !important;
            rotate: 0deg !important;

            margin-left: 50%;
            transform: translateX(-50%);
        }
        :global(.hoverable:hover) {
            transform: translateX(-50%) scale(1.15);
        }
        #my-work_2 {
            margin-top: 20px;
        }
        #main-div {
            padding-top: 0px;
        }
    }

    @media (max-width: 590px) {
        #projects article #image {
            position: absolute;
            top: 2px;
            right: 0;
            width: 90px;
        }
        h1 {
            font-size: 30px;
            line-height: normal;
        }
    }
</style>
