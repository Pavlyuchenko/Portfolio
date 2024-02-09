<section>
    <img loading="lazy" src="ja.jpg" alt="Me, myself and I" id="profile" />
    <div id="personal-info">
        <h1>Hello, I'm <span style="color: var(--primary);">Michal</span></h1>
        <p id="main-desc">
            I'm a Computer Science student from Czechia, who spent a year
            studying Data Science & AI in the Netherlands. Aside from studying,
            I am a full-stack developer, soccer player, and a sci-fi fan.
        </p>
        <p id="desc">
            I used to freelance at Upwork and work for a Czech company
            <a href="https://zauzoo.com" target="_blank">Zauzoo</a>
            as a front-end developer and tester. I created both the front-end and
            the back-end of projects
            <a href="https://velkadomu-sapper.vercel.app" target="_blank">
                VelkáDomů.cz
            </a>
            and
            <a href="https://slibotechny.cz" target="_blank">Slibotechny</a>.
            The main technologies I use are React & Flask.
        </p>
        <p id="desc">
            Currently, I am staring a handfull of projects: a programming club
            at my local high school, a high school programming competition at
            BUT, and revamping non-profit websites. I am looking for a summer
            2024 internship.
        </p>
        <p id="desc">
            Among my biggest competitive programming achievments belongs
            reaching the 20th place in the whole Czechia in both
            <a
                href="https://mo.mff.cuni.cz/p/71/vysledky-3.pdf"
                target="_blank"
            >
                Math olympiad in programming
            </a>
            and another programming competition
            <a
                href="https://kasiopea.matfyz.cz/archiv/2021/finale/vysledky/"
                target="_blank"
            >
                Kasiopea</a
            >.
        </p>
        <p id="desc">
            I would eventually like to end up in the area of sports data science
            or virtual reality. Flipping a coin for it.
        </p>
    </div>
</section>
<div id="skills-wrapper">
    <h3>Skills</h3>
    <hr />
    <div class="skills">
        <div class="grid-column">
            <p>React</p>
            <p>HTML & CSS</p>
            <p>Python</p>
            <p>Flask</p>
            <p>SQL Alchemy</p>
        </div>
        <div class="grid-column">
            <p>Svelte</p>
            <p>Sapper</p>
            <p>KarmaJS</p>
            <p>Jasmine</p>
            <p>SEO</p>
        </div>
        <div class="grid-column">
            <p>Git, Github</p>
            <p>Material UI</p>
            <p>Figma</p>
            <p>Vercel</p>
            <p>Java</p>
            <p>C</p>
        </div>
    </div>
</div>
<div id="skills-wrapper">
    <h3>Achievements</h3>
    <hr />
    <div class="skills">
        <div class="grid-column">
            <b>20th place, national round</b>
            <p style="font-weight: 400;">Maths olympiad in programming</p>
        </div>
        <div class="grid-column">
            <b>20th place, national round</b>
            <p style="font-weight: 400;">Programming competition Kasiopea</p>
        </div>
        <div class="grid-column">
            <b>1st place, national round</b>
            <p style="font-weight: 400;">High School Business Challenge</p>
        </div>
    </div>
</div>
<div id="skills-wrapper">
    <h3>Contact</h3>
    <hr />
    <p id="contact-text">
        Would you like to get in touch with me? Below are the most common ways I
        communicate with others. It would be a pleasure to meet you, feel free
        to contact me!
    </p>
    <div id="links">
        <a href="https://www.linkedin.com/in/michal-pavlicek/" target="_blank">
            <img src="/linkedin.png" alt="LinkedIn logo" />
        </a>
        <a href="mailto:michaelg.pavlicek@gmail.com" target="_blank">
            <img src="/gmail.png" alt="Gmail logo" />
        </a>
        <a href="https://github.com/Pavlyuchenko" target="_blank">
            <img src="/github.png" alt="GitHub logo" />
        </a>
    </div>
</div>

<style>
    section {
        margin-top: 50px;
        padding: 0px calc((100% - 75rem) / 2);

        display: flex;
        justify-content: space-between;
    }
    #profile {
        width: 50%;
    }
    #personal-info {
        width: 47%;
    }
    h3 {
        font-size: 16px;
        color: #666;
        margin-bottom: 12px;
    }
    h1 {
        margin-top: 30px;
        font-size: 40px;
        font-weight: 500;
    }
    #main-desc {
        font-size: 20px;
        line-height: 30px;
    }
    #desc {
        font-size: 18px;
        line-height: 25px;
    }
    #skills-wrapper {
        padding: 0px calc((100% - 75rem) / 2);
        margin-top: 80px;
    }
    .skills {
        grid-template-columns: repeat(3, 1fr);
        display: grid;
        grid-row-gap: 16px;
    }
    .skills p {
        margin-top: 7px;
        margin-bottom: 7px;
        font-weight: 500;
        font-size: 18px;
    }
    #contact-text {
        margin-top: 10px;
        font-size: 18px;
    }
    #links {
        display: flex;
        gap: 50px;
        width: 100%;
        margin-top: 40px;
        justify-content: center;
    }
    #links img {
        height: 80px;
    }

    @media (max-width: 1250px) {
        section {
            display: block;
        }
        #profile {
            max-height: 400px;
            object-fit: cover;
        }
        #personal-info {
            width: 100%;
        }
    }
    @media (max-width: 500px) {
        #profile {
            width: 100%;
            max-height: 500px;
        }
        #links img {
            height: 50px;
        }
        .skills {
            grid-template-columns: repeat(2, 1fr);
            text-align: center;
        }
    }
</style>
