<div id="intro">
    <h1>
        The stories about <br />
        <i id="red-text">Everything</i>
    </h1>
    <div id="right-main">
        <p id="hello">
            You finally stumbled upon my writing space! Thought you'd never
            come...
        </p>
        <div id="vl" style="height: 100%" />
        <p id="bio">
            This blog aims to be all over the place and to make you think.
            Expect topics such as technology, self-improvement, literature,
            personal stories, science-fiction, philosophy.
        </p>
    </div>
</div>
<p id="by-category">By date</p>
<hr />
<div class="by-date">
    <div>
        <h2>2022</h2>
        <div class="by-date-item">
            <h4>October</h4>
            <div>
                <a
                    href="/article/studium-v-zahranici-nizozemsko"
                    class="article-title czech"
                >
                    Studium v zahraničí: Jak se dostat na univerzitu v Nizozemí
                </a>
            </div>
        </div>
    </div>
</div>
<p id="by-category">By category</p>
<hr />
<div class="grid">
    <div class="grid-item">
        <h2>Technology</h2>
        <a href="/writing">Empty</a><br />
    </div>
    <div class="grid-item">
        <h2>Self-Improvement</h2>
        <a href="/writing" disabled>Empty</a><br />
    </div>
    <div class="grid-item">
        <h2>Stories</h2>
        <a href="/article/studium-v-zahranici-nizozemsko" class="czech">
            Studium v zahraničí: Jak se dostat na univerzitu v Nizozemí
        </a><br />
    </div>
    <div class="grid-item">
        <h2>Literature</h2>
        <a href="/article/why-scifi-is-going-to-decline"> Empty </a><br />
    </div>
    <div class="grid-item">
        <h2>Philosophy</h2>
        <a href="/writing" disabled>Empty</a><br />
    </div>
    <div class="grid-item">
        <h2>Other</h2>
        <a href="/writing" disabled>Empty</a><br />
    </div>
</div>

<div id="blank" style="height: 200px;" />

<style>
    #intro {
        display: flex;
        align-items: center;
        height: 100%;
        position: relative;

        margin-top: 75px;
    }

    h1 {
        color: var(--primary);
        font-weight: 700;
        font-family: "Inter", sans-serif;
        font-size: 45px;
        line-height: 67px;

        padding-right: 40px;
        width: 50%;
        margin-top: 0px;
    }
    #red-text {
        color: var(--secondary);
        filter: drop-shadow(2px 2px 0px #888);
    }

    #vl {
        top: 0px;
        left: 50%;
        width: 0;
        border: 0;
        border-left: 2px solid var(--primary);
        position: absolute;
    }
    #right-main {
        width: 45%;
        padding-left: 5%;
    }
    #hello {
        color: var(--primary);
        font-weight: 600;
        font-size: 15px;
    }
    #bio {
        font-size: 19px;
        line-height: 130%;
    }

    #by-category {
        margin-top: 100px;
        font-family: "Inter";
        margin-bottom: 0px;
        font-weight: 500;
        color: var(--primary);
    }
    hr {
        border-top: 2px solid var(--primary);
        margin-bottom: 0px;
    }

    .grid {
        display: grid;
        grid-template-columns: minmax(0, 1fr) minmax(0, 1fr) minmax(0, 1fr);
        grid-template-rows: 1fr;

        max-width: 100%;
    }
    .grid-item {
        text-align: center;
    }
    .grid-item h2 {
        color: var(--secondary);
        font-size: 30px;
        margin-bottom: 10px;
        margin-top: 50px;
    }
    .grid-item a {
        display: inline-block;
        color: var(--primary);
        font-size: 19px;
        font-weight: 500;
        margin-top: 10px;
    }
    .czech {
        position: relative;
    }
    .czech::after {
        content: "";
        display: inline-block;
        position: absolute;
        left: calc(100% + 8px);

        width: 30px;
        height: 20px;
        background: url("/cz.png");
        background-size: 30px 20px;
        border: 1px solid black;
    }

    .by-date {
        padding: 0px calc((100% - 35rem) / 2) 0px;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .by-date h2 {
        margin-top: 50px;
        margin-bottom: 15px;

        font-size: 30px;
        color: var(--secondary);

        align-self: flex-start;
    }
    .by-date-item {
        display: flex;
        align-items: flex-start;
        margin-bottom: 10px;
    }
    .by-date-item h4 {
        min-width: 120px;
        font-weight: 400;
        font-size: 20px;
    }
    .by-date-item a {
        font-size: 18px;
        color: var(--primary);
    }
    .article-title {
        display: inline-block;
        margin-bottom: 10px;
    }

    @media (max-width: 1100px) {
        h1 {
            margin-top: 50px;
        }
        #main-div {
            padding-left: 0px;
        }
        #intro {
            flex-direction: column;
            align-items: center;
        }
        #vl {
            display: none;
        }
        h1 {
            width: 95%;
            text-align: center;
            padding-right: 0;
        }
        #main-div {
            margin-top: 20px;
        }
        #right-main {
            width: 100%;
            margin-top: 10px;
        }
        #hello {
            text-align: left;
            font-size: 20px;
        }
        #bio {
            font-size: 20px;
        }
        .grid {
            grid-template-columns: minmax(0, 1fr) minmax(0, 1fr);
        }
    }

    @media (max-width: 950px) {
        .grid {
            grid-template-columns: minmax(0, 1fr);
        }
    }

    @media (max-width: 590px) {
        h1 {
            font-size: 32px;
            line-height: normal;
        }
    }

    @media (max-width: 360px) {
        #bio {
            font-size: 18px;
        }
    }
</style>
