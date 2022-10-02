<script>
    import { goto } from "@sapper/app";

    function changeBurger() {
        document.getElementById("container").classList.toggle("change");
        if (document.getElementById("links").style.display == "flex") {
            document.getElementById("links").style.display = "none";
        } else {
            document.getElementById("links").style.display = "flex";
        }
    }

    export let segment;
</script>

{#if segment === "showcase"}
    <slot />
{:else}
    <main>
        <nav>
            <div id="left-nav">
                <a href={segment === "cs" ? "/cs" : "/"}>
                    <img
                        src="ja_cropped.jpg"
                        alt="Michal Pavlíček foto"
                        width="64"
                        height="64"
                        style="border-radius: 50%; object-fit: cover;"
                    />
                </a>
                <div id="image-info">
                    <h3>Michal Pavlíček</h3>
                    <p>
                        <span class="checkmark">
                            <div class="checkmark_stem" />
                            <div class="checkmark_kick" />
                        </span>
                        <span id="programator">Programmer</span>
                        <span class="checkmark">
                            <div class="checkmark_stem" />
                            <div class="checkmark_kick" />
                        </span>
                        Web Developer
                    </p>
                </div>
            </div>
            <div id="right-nav">
                <a
                    href={segment === "cs" ? "/cs" : "/"}
                    style="text-decoration: {segment === undefined
                        ? 'underline'
                        : 'none'}; 
					color: {segment === undefined ? 'var(--secondary)' : 'var(--primary)'};"
                >
                    Portfolio
                </a>
                <a
                    href={segment === "cs" ? "/cs/about" : "/about"}
                    style="text-decoration: {segment === 'about'
                        ? 'underline'
                        : 'none'}; color: {segment === 'about'
                        ? 'var(--secondary)'
                        : 'var(--primary)'};"
                >
                    About
                </a>
                <a
                    href="/writing"
                    style="text-decoration: {segment === 'writing'
                        ? 'underline'
                        : 'none'}; color: {segment === 'writing'
                        ? 'var(--secondary)'
                        : 'var(--primary)'};"
                >
                    Writing
                </a>
                <a
                    href={segment === "cs" ? "/cs/resume" : "/resume"}
                    style="text-decoration: {segment === 'resume'
                        ? 'underline'
                        : 'none'}; color: {segment === 'resume'
                        ? 'var(--secondary)'
                        : 'var(--primary)'};"
                >
                    Resumé
                </a>
                <a
                    href={segment === "cs" ? "/" : "/cs"}
                    style="text-decoration: 'none'; color: 'var(--secondary)';"
                >
                    {#if segment === "cs"}
                        <img
                            loading="lazy"
                            src="https://ik.imagekit.io/velkadomu/uk__ckmO6dTr.svg?ik-sdk-version=javascript-1.4.3&updatedAt=1649504369963"
                            alt="English"
                            width="28"
                        />
                    {:else}
                        <img
                            src="cz.png"
                            alt="Česky"
                            width="28"
                            style="border: 1px solid black;"
                        />
                    {/if}
                </a>
            </div>
        </nav>
        <hr />
        <div id="mobile-nav">
            <div
                id="left-nav"
                on:click={() => {
                    goto("/");
                    document.getElementById("links").style.display = "none";
                    document.getElementById("container").classList = "";
                }}
            >
                <img
                    src="ja_cropped.jpg"
                    alt="Michal Pavlíček foto"
                    width="32"
                    height="32"
                    id="mobile-profile-img"
                />
                <div id="image-info">
                    <h3>Michal Pavlíček</h3>
                </div>
            </div>
            <div id="right-nav">
                <div
                    id="container"
                    on:click={() => {
                        changeBurger();
                    }}
                >
                    <div class="bar1" />
                    <div class="bar2" />
                    <div class="bar3" />
                </div>
            </div>
        </div>
        <div
            id="links"
            on:click={() => {
                document.getElementById("links").style.display = "none";
                document.getElementById("container").classList = "";
            }}
        >
            <a href={segment === "cs" ? "/cs" : "/"}>Portfolio</a>
            <a href={segment === "cs" ? "/cs/about" : "/about"}>About</a>
            <a href={segment === "cs" ? "/cs/resume" : "/resume"}>Resumé</a>
            <a
                href={segment === "cs" ? "/" : "/cs"}
                style="text-decoration: 'none'; color: 'var(--secondary)';"
            >
                {#if segment === "cs"}
                    <img
                        loading="lazy"
                        src="https://ik.imagekit.io/velkadomu/uk__ckmO6dTr.svg?ik-sdk-version=javascript-1.4.3&updatedAt=1649504369963"
                        alt="English"
                        width="28"
                    />
                {:else}
                    <img
                        src="cz.png"
                        alt="Česky"
                        width="28"
                        style="border: 1px solid black;"
                    />
                {/if}
            </a>
            <hr id="mobile-hr" />
        </div>
        <slot />

        {#if segment !== "writing"}
            <footer>
                <div id="text">
                    <h2>Let's create something together!</h2>
                    <p>
                        Do you have an interesting idea, need help with
                        something or just want to get in touch with me?
                        <br />
                        Feel free to write me an email, I'm happy to join even smaller
                        projects!
                    </p>
                    <br />
                    <a
                        href="https://mail.google.com/mail/u/0/?fs=1&to=michaelg.pavlicek@gmail.com&su=Chci s tebou spolupracovat!&tf=cm"
                        target="_blank"
                    >
                        michaelg.pavlicek@gmail.com
                    </a>
                </div>
                <div id="thanks">
                    Portfolio heavily inspired by
                    <a href="https://taamannae.dev/">Tammy Taabassum</a>.
                </div>
            </footer>
        {/if}
    </main>
{/if}

<style>
    #thanks {
        position: absolute;
        bottom: 15px;
        right: 15px;

        font-size: 14px;
    }
    #thanks a {
        font-size: 14px;
        margin: 0 !important;
    }
    nav {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    img {
        display: inline-block;
        vertical-align: middle;

        cursor: pointer;
    }
    #image-info {
        display: inline-block;
        vertical-align: middle;

        margin-left: 15px;
        margin-top: 5px;
    }
    h3 {
        font-weight: 600;
        font-size: 1.5em;

        margin-bottom: 0px;
    }
    p {
        margin: 0;
        font-weight: 600;

        display: inline-block;
        vertical-align: middle;
    }
    .checkmark {
        display: inline-block;
        vertical-align: middle;

        width: 25px;
        height: 30px;

        -ms-transform: rotate(45deg);
        -webkit-transform: rotate(45deg);
        transform: rotate(45deg);

        margin-right: 0px;
    }
    .checkmark_stem {
        position: absolute;
        width: 4px;
        height: 13px;
        background-color: var(--secondary);
        left: 11px;
        top: 6px;
    }
    .checkmark_kick {
        position: absolute;
        width: 5px;
        height: 4px;
        background-color: var(--secondary);
        left: 7px;
        top: 15px;
    }
    #programator {
        margin-right: 7px;
    }

    #right-nav a {
        text-decoration: none;
        margin-left: 60px;

        font-size: 16px;
        font-weight: 600;
        color: var(--primary);

        transition: 0.1s;
    }

    #right-nav a:hover {
        color: var(--secondary);
    }

    hr {
        border: 0;
        border-top: 2px solid var(--primary);

        margin-top: 20px;
    }

    #mobile-nav {
        display: none;
    }

    #mobile-profile-img {
        border-radius: 50%;
        object-fit: cover;
    }

    #links {
        display: none;
    }

    footer {
        background-color: var(--primary);
        margin-top: 80px;
        position: absolute;
        height: 300px;
        left: 0;

        padding: 0px calc((100% - 73rem) / 2) 0px calc((100% - 73rem) / 2);
        width: calc(100% - ((100% - 73rem) / 2) * 2);

        color: #ffffff;
    }
    footer #text {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
    }

    footer h2 {
        font-family: "Inter";
        font-weight: 500;
        font-size: 34px;

        margin-bottom: 20px;
    }
    footer p {
        font-weight: 400;
        line-height: 25px;

        margin-bottom: 20px;
    }
    footer a {
        font-family: "Inter";
        font-weight: 500;
        font-size: 22px;
    }
    @media (max-width: 1100px) {
        footer {
            width: 100%;
            height: 300px;
        }
        footer h2 {
            font-size: 24px;
            margin-right: 20px;
            margin-left: 20px;
        }
        footer p {
            font-size: 16px;
            margin-right: 20px;
            margin-left: 20px;
        }
        footer a {
            font-size: 20px;
            margin-right: 20px;
            margin-left: 20px;
        }
    }

    @media (max-width: 1000px) {
        nav,
        hr {
            display: none;
        }

        #mobile-nav {
            display: flex;
            justify-content: space-between;
        }
        h3 {
            font-size: 20px;
            margin-top: -5px;
        }

        #container {
            display: inline-block;
            cursor: pointer;
        }

        .bar1,
        .bar2,
        .bar3 {
            width: 30px;
            height: 4px;
            background-color: var(--primary);
            margin-bottom: 5px;
            transition: 0.4s;
        }

        :global(.change .bar1) {
            -webkit-transform: rotate(-45deg) translate(-9px, 6px);
            transform: rotate(-45deg) translate(-5px, 5px);
        }

        :global(.change .bar2) {
            opacity: 0;
        }

        :global(.change .bar3) {
            -webkit-transform: rotate(45deg) translate(-8px, -8px);
            transform: rotate(45deg) translate(-8px, -8px);
        }

        #links {
            flex-direction: column;
            align-items: center;
        }
        #links a {
            margin-top: 20px;
            color: var(--primary);
            font-size: 20px;
        }
        #mobile-hr {
            display: block;
            border-top: 2px solid var(--primary);
            width: 100%;
        }
    }
</style>
