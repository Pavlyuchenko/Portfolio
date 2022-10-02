<script>
    import { onMount } from "svelte";

    /*
		--------------------------------------------------------------------------------------------------------------|
		|	Each block has pretty much the same structure
		|		* id : int primary key
		|		* content : string
		|		* type : "p" | "h1" | "h2" | "h3" | "bullet" | "callout" | "quote" | "image" | "twitter" | "youtube"
		|		* ? src : string
		|			-> Only if type === "image"
		|		* ? tweet : string
		|			-> Only if type === "twitter"
		|		* ? url : string
		|			-> Only if type === "youtube"
		--------------------------------------------------------------------------------------------------------------|
	*/
    export let blocks = [{ id: 1, content: "Start typing...", type: "p" }];
    // blocks array MUST contain at least 1 object of such structure: {id: int, content: string, type: type}

    export let mainColor = "#6495ED";
    export let textColor = "#121212";
    export let showTutorial = false;

    let focusedEl = 0;
    $: cursorPos = 0;
    $: canDelete = true;

    onMount(() => {
        var r = document.querySelector(":root");
        r.style.setProperty("--main-color", mainColor);
        r.style.setProperty("--text-color", textColor);

        document.addEventListener(
            "keydown",
            function (e) {
                if (
                    e.key == "s" &&
                    (navigator.platform.match("Mac") ? e.metaKey : e.ctrlKey)
                ) {
                    e.preventDefault();
                    sendData();
                }
            },
            false
        );
        document.addEventListener("click", (e) => {
            for (let i = 0; i < blocks.length; i++) {
                try {
                    const options = document.getElementById(
                        "options-p" + (i + 1)
                    );

                    const optionsMenu = document.getElementById(
                        "options-menu" + (i + 1)
                    );
                    if (!(e.target === options)) {
                        optionsMenu.style.display = "none";
                    }
                } catch (error) {
                    console.log(error);
                }
            }
        });
    });

    function updateIndex(event, element) {
        if (element.contains(event.target)) {
            cursorPos = getCaretIndex(element).toString();
        } else {
            cursorPos = "–";
        }
    }

    function getCaretIndex(element) {
        let position = 0;
        const isSupported = typeof window.getSelection !== "undefined";
        if (isSupported) {
            const selection = window.getSelection();
            // Check if there is a selection (i.e. cursor in place)
            if (selection.rangeCount !== 0) {
                // Store the original range
                const range = window.getSelection().getRangeAt(0);
                // Clone the range
                const preCaretRange = range.cloneRange();
                // Select all textual contents from the contenteditable element
                preCaretRange.selectNodeContents(element);
                // And set the range end to the original clicked position
                preCaretRange.setEnd(range.endContainer, range.endOffset);
                // Return the text length from contenteditable start to the range end
                position = preCaretRange.toString().length;
            }
        }
        return position;
    }

    function placeCaretAtEnd(el) {
        el.focus();
        if (
            typeof window.getSelection != "undefined" &&
            typeof document.createRange != "undefined"
        ) {
            var range = document.createRange();
            range.selectNodeContents(el);
            range.collapse(false);
            var sel = window.getSelection();
            sel.removeAllRanges();
            sel.addRange(range);
        } else if (typeof document.body.createTextRange != "undefined") {
            var textRange = document.body.createTextRange();
            textRange.moveToElementText(el);
            textRange.collapse(false);
            textRange.select();
        }
    }

    function blockChange(e, id) {
        let block = blocks.find((x) => x.id === id);

        // Heading 1
        if (
            block.content.substring(0, 7) === "#&nbsp;" ||
            block.content.substring(0, 9) === "/h1&nbsp;"
        ) {
            block.type = "h1";
            block.content = "";
            blocks = [...blocks];
        } else if (block.content.substring(0, 2) === "# ") {
            block.type = "h1";
            block.content = block.content.substring(2);
            blocks = [...blocks];
        } else if (block.content.substring(0, 4) === "/h1 ") {
            block.type = "h1";
            block.content = block.content.substring(4);
            blocks = [...blocks];
        }
        // Heading 2
        else if (
            block.content === "##&nbsp;" ||
            block.content === "/h2&nbsp;"
        ) {
            block.type = "h2";
            block.content = "";
            blocks = [...blocks];
        } else if (block.content.substring(0, 3) === "## ") {
            block.type = "h2";
            block.content = block.content.substring(3);
            blocks = [...blocks];
        } else if (block.content.substring(0, 4) === "/h2 ") {
            block.type = "h2";
            block.content = block.content.substring(4);
            blocks = [...blocks];
        }
        // Heading 3
        else if (
            block.content === "###&nbsp;" ||
            block.content === "/h3&nbsp;"
        ) {
            block.type = "h3";
            block.content = "";
            blocks = [...blocks];
        } else if (block.content.substring(0, 4) === "### ") {
            block.type = "h3";
            block.content = block.content.substring(4);
            blocks = [...blocks];
        } else if (block.content.substring(0, 4) === "/h3 ") {
            block.type = "h3";
            block.content = block.content.substring(4);
            blocks = [...blocks];
        }
        // Callout
        else if (
            block.content === "&gt;&nbsp;" ||
            block.content === "/z&nbsp;"
        ) {
            block.type = "callout";
            block.content = "";
            blocks = [...blocks];
        } else if (block.content.substring(0, 5) === "&gt; ") {
            block.type = "callout";
            block.content = block.content.substring(5);
            blocks = [...blocks];
        } else if (block.content.substring(0, 3) === "/z ") {
            block.type = "callout";
            block.content = block.content.substring(3);
            blocks = [...blocks];
        }
        // quote
        else if (block.content === "|&nbsp;" || block.content === "/c&nbsp;") {
            block.type = "quote";
            block.content = "";
            blocks = [...blocks];
        } else if (block.content.substring(0, 2) === "| ") {
            block.type = "quote";
            block.content = block.content.substring(2);
            blocks = [...blocks];
        } else if (block.content.substring(0, 3) === "/c ") {
            block.type = "quote";
            block.content = block.content.substring(3);
            blocks = [...blocks];
        }
        // Bullet point
        else if (block.content === "*&nbsp;" || block.content === "/o&nbsp;") {
            block.type = "bullet";
            block.content = "";
            blocks = [...blocks];
        } else if (block.content.substring(0, 2) === "* ") {
            block.type = "bullet";
            block.content = block.content.substring(2);
            blocks = [...blocks];
        } else if (block.content.substring(0, 3) === "/o ") {
            block.type = "bullet";
            block.content = block.content.substring(3);
            blocks = [...blocks];
        }
        // Image
        else if (
            block.content == "/img&nbsp;" ||
            block.content == "/image&nbsp;" ||
            block.content == "/image&nbsp;"
        ) {
            block.type = "image";
            block.content = "";
            block.url = "Enter image URL";
            blocks = [...blocks];

            if (id == blocks.length) {
                for (let index = id; index < blocks.length; index++) {
                    blocks[index].id++;
                }

                blocks.splice(id, 0, { id: id + 1, content: "", type: "p" });

                blocks = [...blocks];
            }

            setTimeout(() => {
                let el = document.getElementById("block" + id);
                el.focus();

                document
                    .getElementById("block" + id)
                    .addEventListener("paste", function (event) {
                        event.preventDefault();
                        document.execCommand(
                            "inserttext",
                            false,
                            event.clipboardData.getData("text/plain")
                        );
                    });
            }, 1);

            blocks = blocks;
        }
        // Twitter
        else if (
            block.content == "/twit&nbsp;" ||
            block.content == "/tweet&nbsp;"
        ) {
            block.type = "twitter";
            block.content = "";
            block.tweet = "Enter Tweet...";
            blocks = [...blocks];

            if (id == blocks.length) {
                for (let index = id; index < blocks.length; index++) {
                    blocks[index].id++;
                }

                blocks.splice(id, 0, { id: id + 1, content: "", type: "p" });

                blocks = [...blocks];
            }

            setTimeout(() => {
                let el = document.getElementById("block" + id);
                el.focus();

                document
                    .getElementById("block" + id)
                    .addEventListener("paste", function (event) {
                        event.preventDefault();
                        document.execCommand(
                            "inserttext",
                            false,
                            event.clipboardData.getData("text/plain")
                        );
                    });
            }, 1);
        }
        // Video
        else if (
            block.content == "/vid&nbsp;" ||
            block.content == "/you&nbsp;" ||
            block.content == "/ytb&nbsp;"
        ) {
            block.type = "youtube";
            block.content = "";
            block.url = "Enter video ID...";
            blocks = [...blocks];

            if (id == blocks.length) {
                for (let index = id; index < blocks.length; index++) {
                    blocks[index].id++;
                }

                blocks.splice(id, 0, { id: id + 1, content: "", type: "p" });

                blocks = [...blocks];
            }

            setTimeout(() => {
                let el = document.getElementById("block" + id);
                el.focus();

                document
                    .getElementById("block" + id)
                    .addEventListener("paste", function (event) {
                        event.preventDefault();
                        document.execCommand(
                            "inserttext",
                            false,
                            event.clipboardData.getData("text/plain")
                        );
                    });
            }, 1);
        }
        /* setTimeout(() => {
			let el = document.getElementById("block" + id);
			el.focus();
			document
				.getElementById("block" + id)
				.addEventListener("paste", function (event) {
					event.preventDefault();
					document.execCommand(
						"inserttext",
						false,
						event.clipboardData.getData("text/plain")
					);
				});
		}, 1); */
    }

    function keyDown(e, id) {
        let block = blocks.find((x) => x.id === id);

        updateIndex(e, document.getElementById("block" + id));

        if (
            !e.ctrlKey &&
            e.key == "Backspace" &&
            block.type != "p" &&
            cursorPos == 0 &&
            canDelete
        ) {
            setTimeout(() => {
                let el = document.getElementById("block" + id);
                el.focus();

                document
                    .getElementById("block" + id)
                    .addEventListener("paste", function (event) {
                        event.preventDefault();
                        document.execCommand(
                            "inserttext",
                            false,
                            event.clipboardData.getData("text/plain")
                        );
                    });
            }, 1);

            block.type = "p";
            blocks = [...blocks];
        } else if (
            e.key == "Backspace" &&
            (block.content == "" ||
                block.content == "<br />" ||
                block.content == "<br>") &&
            !e.ctrlKey &&
            canDelete
        ) {
            if (
                block.type != "image" &&
                block.type != "twitter" &&
                block.type != "youtube"
            ) {
                deleteBlock(id);
            } else if (block.url == "" || block.tweet == "") {
                deleteBlock(id);
            }
        } else if (e.key == "Enter") {
            e.preventDefault();
            createBlock(id);
        } else if (e.key == "ArrowUp" && focusedEl != 1) {
            if (cursorPos == 0) {
                let el = document.getElementById("block" + (id - 1));
                el.focus();
                placeCaretAtEnd(el);
            }
        } else if (e.key == "ArrowUp" && focusedEl == 1) {
            if (cursorPos == 0) {
                createBlockAbove();
            }
        } else if (e.key == "ArrowDown" && focusedEl != blocks.length) {
            if (
                block.content.length - 1 == parseInt(cursorPos) ||
                block.content.length == 0 ||
                block.content.length == parseInt(cursorPos)
            ) {
                let el = document.getElementById("block" + (id + 1));
                el.focus();
                //placeCaretAtEnd(el);
            }
        } else if (e.key == "ArrowDown" && focusedEl == blocks.length) {
            if (
                block.content.length - 1 == parseInt(cursorPos) ||
                block.content.length == 0 ||
                block.content.length == parseInt(cursorPos)
            ) {
                createBlock(blocks.length);
            }
        }

        canDelete = true;
        blocks = blocks;
    }

    function createBlock(id) {
        for (let index = id; index < blocks.length; index++) {
            blocks[index].id++;
        }

        blocks.splice(id, 0, { id: id + 1, content: "", type: "p" });

        blocks = [...blocks];

        setTimeout(() => {
            let el = document.getElementById("block" + (id + 1));

            el.focus();
            el.addEventListener("paste", function (event) {
                event.preventDefault();
                document.execCommand(
                    "inserttext",
                    false,
                    event.clipboardData.getData("text/plain")
                );
            });
            document.getElementById("options-menu" + (id + 1)).style.display =
                "none";
        }, 1);
    }

    function createBlockAbove() {
        for (let index = 0; index < blocks.length; index++) {
            blocks[index].id++;
        }

        blocks.splice(0, 0, { id: 1, content: "", type: "p" });

        blocks = [...blocks];

        setTimeout(() => {
            let el = document.getElementById("block1");

            el.focus();
            el.addEventListener("paste", function (event) {
                event.preventDefault();
                document.execCommand(
                    "inserttext",
                    false,
                    event.clipboardData.getData("text/plain")
                );
            });
        }, 1);
    }

    function deleteBlock(id) {
        if (blocks.length != 1) {
            blocks.splice(id - 1, 1);
            blocks = [...blocks];

            for (let index = id - 1; index < blocks.length; index++) {
                blocks[index].id--;
            }
            setTimeout(() => {
                let el;
                if (id != 1) {
                    el = document.getElementById("block" + (id - 1));
                } else {
                    el = document.getElementById("block" + id);
                }
                el.focus();
                placeCaretAtEnd(el);
            }, 1);
        }
    }

    function turnInto(type, id) {
        let block = blocks.find((x) => x.id === id);

        block.type = type;
        document.getElementById("block" + id).focus();
        placeCaretAtEnd(document.getElementById("block" + id));

        blocks = [...blocks];
    }
</script>

<div id="flex-container">
    {#if showTutorial}
        <aside>
            <div id="tutorial">
                <p># or /h1 - Main subheading</p>
                <p>## or /h2 - Secondary subheading</p>
                <p>### or /h3 - Terciary subheading</p>
                <p>* or /o - Bullet point</p>
                <p>| or /c - Citation</p>
                <p>&gt; or /z - Highlight</p>
                <p>Cursive - Ctrl + i (or &text/&)</p>
                <p>Bold - Ctrl + b (or @text/@)</p>
                <p>Underline - Ctrl + u</p>
                <p>/img - Image</p>
                <p>/tweet - Tweet (embed)</p>
                <p>/ytb - Video (embed)</p>
            </div>
        </aside>
    {/if}
    <section>
        {#each blocks as block}
            {#if block.type == "image"}
                <div
                    contenteditable="true"
                    bind:innerHTML={block.url}
                    on:blur={() => {
                        focusedEl = 0;
                    }}
                    on:focus={() => {
                        focusedEl = block.id;
                    }}
                    on:focus|once={() => {
                        if (
                            block.url == "Enter image URL" ||
                            block.url == "undefined"
                        ) {
                            block.url = "";
                        }
                    }}
                    on:keydown={(e) => keyDown(e, block.id)}
                    id={"block" + block.id}
                    class="image"
                >
                    {block.url}
                </div>
            {:else if block.type == "twitter"}
                <div
                    contenteditable="true"
                    bind:innerHTML={block.tweet}
                    on:blur={() => {
                        focusedEl = 0;
                    }}
                    on:focus={() => {
                        focusedEl = block.id;
                    }}
                    on:focus|once={() => {
                        if (
                            block.tweet == "Enter Tweet..." ||
                            block.tweet == "undefined"
                        ) {
                            block.tweet = "";
                        }
                    }}
                    on:keydown={(e) => keyDown(e, block.id)}
                    id={"block" + block.id}
                    class="image twitter-blue"
                >
                    {block.tweet}
                </div>
            {:else if block.type == "youtube"}
                <div
                    contenteditable="true"
                    bind:innerHTML={block.url}
                    on:blur={() => {
                        focusedEl = 0;
                    }}
                    on:focus={() => {
                        focusedEl = block.id;
                    }}
                    on:focus|once={() => {
                        if (
                            block.url == "Enter video ID..." ||
                            block.url == "undefined"
                        ) {
                            block.url = "";
                        }
                    }}
                    on:keydown={(e) => keyDown(e, block.id)}
                    id={"block" + block.id}
                    class="image youtube-red"
                >
                    {block.url}
                </div>
            {:else}
                <div
                    class="options-container"
                    on:mouseover={() =>
                        (document.getElementById(
                            "options-p" + block.id
                        ).innerHTML = "&nbsp;=")}
                    on:mouseleave={() => {
                        if (
                            document.getElementById("options-menu" + block.id)
                                .style.display == "none"
                        ) {
                            document.getElementById(
                                "options-p" + block.id
                            ).innerHTML = "&nbsp;";
                        }
                    }}
                >
                    <div
                        bind:innerHTML={block.content}
                        on:click={(e) => {
                            updateIndex(
                                e,
                                document.getElementById("block" + block.id)
                            );
                        }}
                        on:keydown={(e) => {
                            if (e.key == "Enter") {
                                e.preventDefault();
                            } else if (
                                e.key == "Backspace" &&
                                block.content.length >= 1 &&
                                cursorPos != 0
                            ) {
                                canDelete = false;
                            } else if (
                                (e.key == "b" ||
                                    e.key == "u" ||
                                    e.key == "i") &&
                                e.ctrlKey
                            ) {
                                // e.preventDefault();
                            } else if (e.metaKey && e.key == "b") {
                                document.execCommand("Bold", false, null);
                            } else if (e.metaKey && e.key == "u") {
                                document.execCommand("Underline", false, null);
                            } else if (e.metaKey && e.key == "i") {
                                document.execCommand("Italic", false, null);
                            }
                            blocks = blocks;
                        }}
                        on:keyup={(e) => {
                            keyDown(e, block.id);
                            blocks = blocks;
                        }}
                        on:input={(e) => {
                            blockChange(e, block.id);
                            blocks = blocks;
                        }}
                        on:blur={() => {
                            focusedEl = 0;
                        }}
                        on:focus|once={() => {
                            if (block.content == "Start typing...") {
                                block.content = "";
                            }
                        }}
                        on:focus={() => {
                            focusedEl = block.id;
                        }}
                        class={block.type +
                            " editor block " +
                            (block.content == "Start typing..."
                                ? "placeholder"
                                : "")}
                        id={"block" + block.id}
                        contenteditable="true"
                    >
                        {block.content}
                    </div>

                    <div
                        class="options"
                        id={"options" + block.id}
                        on:click={() => {
                            if (
                                document.getElementById(
                                    "options-menu" + block.id
                                ).style.display == "inline"
                            ) {
                                document.getElementById(
                                    "options-menu" + block.id
                                ).style.display = "none";
                            } else {
                                document.getElementById(
                                    "options-menu" + block.id
                                ).style.display = "inline";
                                document.getElementById(
                                    "options-p" + block.id
                                ).innerHTML = "&nbsp;=";
                            }
                        }}
                    >
                        <p id={"options-p" + block.id}>&nbsp;</p>
                        <div
                            class="options-menu"
                            style="display: none;"
                            id={"options-menu" + block.id}
                        >
                            <div
                                on:click={() => {
                                    turnInto("p", block.id);
                                }}
                            >
                                Text
                            </div>
                            <div
                                on:click={() => {
                                    turnInto("h1", block.id);
                                }}
                            >
                                Heading 1
                            </div>
                            <div
                                on:click={() => {
                                    turnInto("h2", block.id);
                                }}
                            >
                                Heading 2
                            </div>
                            <div
                                on:click={() => {
                                    turnInto("h3", block.id);
                                }}
                            >
                                Heading 3
                            </div>
                            <div
                                on:click={() => {
                                    turnInto("bullet", block.id);
                                }}
                            >
                                Bullet point
                            </div>
                            <div
                                on:click={() => {
                                    turnInto("quote", block.id);
                                }}
                            >
                                Quote
                            </div>
                            <div
                                on:click={() => {
                                    turnInto("callout", block.id);
                                }}
                            >
                                Callout
                            </div>
                            {#if block.content == "" || block.content == "Start typing..."}
                                <div
                                    on:click={() => {
                                        turnInto("image", block.id);
                                    }}
                                >
                                    Image
                                </div>
                            {/if}
                            {#if block.content == "" || block.content == "Start typing..."}
                                <div
                                    on:click={() => {
                                        turnInto("twitter", block.id);
                                    }}
                                >
                                    Tweet
                                </div>
                            {/if}
                            {#if block.content == "" || block.content == "Start typing..."}
                                <div
                                    on:click={() => {
                                        turnInto("youtube", block.id);
                                    }}
                                >
                                    Video
                                </div>
                            {/if}
                            <div
                                on:click={() => {
                                    deleteBlock(block.id);
                                }}
                            >
                                Delete
                            </div>
                        </div>
                    </div>
                </div>
            {/if}
        {/each}
    </section>
</div>

<style>
    [contenteditable] {
        -webkit-user-select: text;
        user-select: text;
    }
    .placeholder {
        color: #bbb !important;
    }
    #flex-container {
        display: flex;
        color: var(--text-color);
    }
    section {
        width: 100%;
        margin: 0 auto;

        position: relative;
    }

    .image {
        width: 100%;
        min-height: 50px;

        display: flex;
        justify-content: center;
        flex-direction: column;
        align-content: center;

        background-color: transparent;
        border: 1px solid #8d8d8d;

        border-radius: 5px;

        margin-top: 10px;
        margin-bottom: 20px;

        box-sizing: border-box;
        padding-left: 20px;
        padding-right: 20px;
        color: #8d8d8d;
        font-weight: 600;
    }

    p,
    div {
        font-size: calc(0.5vw + 11px);
        outline: none;
        box-shadow: none;
        text-align: justify;
    }

    .block {
        transition: 0.2s;
        border-radius: 3px;
        padding-left: 5px;
        padding-right: 5px;
        padding-top: 2px;
        padding-bottom: 2px;
    }
    .block:hover {
        background-color: #f5f5f5;
    }
    .block:focus {
        background-color: #f9f9f9;
    }

    .h1 {
        font-size: 34px;
        font-weight: 700;
    }
    .h2 {
        font-size: 28px;
        font-weight: 600;
    }
    .h3 {
        font-size: 22px;
        font-weight: 600;
    }
    .callout {
        background-color: var(--main-color);
        color: #ffffff;

        padding: 10px;
        padding-left: 15px;
        padding-right: 15px;
    }
    .callout:hover {
        background-color: var(--main-color);
    }
    .callout:focus {
        background-color: var(--main-color);
    }
    .quote {
        padding: 0px;
        padding-left: 15px;
        font-style: italic;
        position: relative;
    }
    .quote::before {
        content: "";
        position: absolute;
        left: 0px;

        width: 5px;
        height: 100%;
        background-color: var(--main-color);
    }
    .bullet {
        padding-left: 30px;
        position: relative;
    }
    .bullet::before {
        content: "";
        position: absolute;
        left: 15px;
        top: 50%;

        width: 5px;
        height: 5px;
        border-radius: 50%;
        background-color: #333333;
    }

    .container {
        display: block;
        position: relative;
        padding-left: 40px;
        padding-top: 0px;
        margin-bottom: 0px;
        cursor: pointer;
        font-size: 24px;
        font-weight: 600;
        -webkit-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
    }
    @media only screen and (max-width: 680px) {
        section {
            width: 100%;
            margin-top: 25px;
        }
        .quote::before {
            width: 3px;
        }
    }

    .options-container {
        position: relative;
    }

    .options {
        position: absolute;
        left: -30px;
        top: 0px;

        line-height: 90%;
        margin: 0;
        padding: 0;
        height: 100%;
        width: 30px;

        cursor: pointer;
        font-size: 30px;
    }
    .options p {
        font-size: 30px;
        height: 100%;
        margin: 0;
        margin-top: -15px;
        padding: 0;
        position: absolute;
        top: 50%;
    }

    .options-menu {
        display: none;
        position: absolute;
        left: 100%;
        top: 0;

        padding: 0;
        margin: 0;
        height: auto;
        width: 150px;

        background-color: #ffffff;
        border: 1px solid #e0e0e0;
        border-radius: 3px;

        cursor: auto;

        box-shadow: 0px 0px 8px #cecece;
    }

    .options-menu div {
        font-size: 18px;

        cursor: pointer;
        transition: 0.1s;
        padding-left: 8px;
    }
    .options-menu div:hover {
        background-color: #e0e0e0;
    }

    .twitter-blue {
        background-color: #1da1f2;
        border-color: #1da1f2;
        color: #ffffff;
    }
    .youtube-red {
        background-color: #ff0000;
        border-color: #ff0000;
        color: #ffffff;
    }
    aside {
        width: 22.5%;

        color: #b7b7b7;
    }
    aside p {
        font-size: 16px;
        margin-top: 5px;
        margin-bottom: 0;
    }
</style>
