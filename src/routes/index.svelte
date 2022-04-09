<script>
	import { onMount } from "svelte";

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

		setTimeout(() => {
			if (document.getElementById("country").innerHTML != "Czechia") {
				foreigner = true;
			}
		}, 500);
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
		"I program mainly in Python and Javascript",
		"the meaning of life is 42",
		"I know Flask, React, Svelte and Sapper",
		"I enjoy designing",
		"I speak English, Czech und ein bisschen Deutsch",
		"I love Sci-fi",
		"I would like to study in Netherlands",
	];

	let variableText = textOptions[textOptionsIndex];
	let cursor;
</script>

<div id="main-div">
	<div id="intro">
		<h1>
			My name is Michael and <br />
			<span id="changing-text">
				{variableText}<span bind:this={cursor} id="cursor">|</span>
			</span>
		</h1>
		<div id="right-main">
			<p id="hello">Hello! Welcome to my portfolio!</p>
			<div id="vl" style="height: {height}px" />
			<p id="bio">
				I am a high school student who programes. I mainly create
				websites from design all the way the back-end. Currently, I
				focus on programming competitions, expanding my portfolio with
				interesting projects and working @ Zauzoo
			</p>
		</div>
	</div>

	<p id="my-work">3 interesting demos</p>
	<hr />

	<div id="demos">
		<a
			href="/showcase/text-editor"
			target="_blank"
			class="demo-item"
			id="text-editor-demo"
		>
			Block-based text editor
		</a>
		<a
			href="https://www.slibotechny.cz/"
			target="_blank"
			class="demo-item"
			id="slibotechny-demo"
		>
			Slibotechny.cz
		</a>
		<br />
		<a
			href="https://codepen.io/Pavlyuchenko/pen/bGaMYgr"
			target="_blank"
			class="demo-item"
			id="sir-demo"
		>
			Pandemic simulation
		</a>
	</div>

	<p id="my-work">My work</p>
	<hr />

	<div class="projects-row">
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
	</div>
	<div class="projects-row">
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
					src="slibotechny_sliced.png"
					alt="Obrázek Slibotechny"
				/>
			</article>
		</a>
	</div>
	<div class="projects-row">
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
					src="vfb_image.png"
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
					src="sir_image.png"
					alt="Obrázek VelkáDomů.cz"
				/>
			</article>
		</a>
	</div>
	<div class="projects-row">
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
					src="pj_image.png"
					alt="Obrázek VelkáDomů.cz"
				/>
			</article>
		</a>
	</div>
</div>

<style>
	#demos {
		display: flex;
		justify-content: space-between;
	}
	.demo-item {
		background-color: red;
		width: 32%;
		height: 50px;
		line-height: 50px;
		border-radius: 4px;
		text-align: center;

		font-size: 20px;
		font-weight: 600;

		transition: 0.25s;
		cursor: pointer;
	}
	.demo-item:hover {
		transform: scale(1.05);
		box-shadow: 4px 4px 18px 8px rgba(33, 33, 33, 0.25);
	}
	#text-editor-demo {
		background-color: #ff8a00;
		color: #fff;
	}
	#slibotechny-demo {
		background: url("/slibotechny.png");
		border: 3px solid #303030;
		box-sizing: border-box;
	}
	#sir-demo {
		background-color: #303030;
		color: #fff;
	}
	#main-div {
		padding: 0px calc((100% - 73rem) / 2) 0px calc((100% - 73rem) / 2);

		position: relative;

		margin-top: 120px;
	}

	#intro {
		display: flex;
	}

	h1 {
		color: var(--primary);
		font-weight: 700;
		font-family: "Inter", sans-serif;
		font-size: 45px;
		line-height: 67px;

		padding-right: 40px;
		width: 50%;
		margin-top: 20px;
	}
	#changing-text {
		color: var(--secondary);
	}
	#cursor {
		color: var(--primary);
	}

	#vl {
		top: -30px;
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
		font-weight: 500;
		font-size: 15px;
	}
	#bio {
		font-size: 19px;
		line-height: 130%;
	}

	#my-work {
		margin-top: 80px;
		font-family: "Inter";
		margin-bottom: 0px;
		font-weight: 500;
		color: var(--primary);
	}
	hr {
		border-top: 2px solid var(--primary);
		margin-bottom: 40px;
	}

	.projects-row {
		display: flex;
		justify-content: space-between;
	}
	.projects-row article {
		width: calc(100%-75px);
		height: 280px;

		margin-bottom: 25px;
		padding: 25px 35px;
		padding-right: 0;

		border-radius: 4px;
		background-color: grey;

		display: flex;
		align-items: center;

		cursor: pointer;
		transition: 0.25s cubic-bezier(0, 0, 0.4, 1);
	}
	.projects-row a {
		width: 49%;
		text-decoration: none;
	}
	.projects-row article:hover {
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

	.projects-row article #image {
		object-fit: cover;
		width: 100%;
		flex: 1;
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

	#expobank {
		background-color: #00465a;
		color: #fff;
		font-weight: 500;
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

	#language-switch {
		position: fixed;
		bottom: 10px;
		left: 10px;
		z-index: 10000;

		padding: 10px 20px;
		background-color: var(--secondary);
		color: #ffffff;
		border-radius: 5px;
		border: 5px solid #000000;

		text-align: center;
		transition: 0.2s;
	}
	#language-switch:hover {
		background-color: var(--primary);
	}
	#language-switch span {
		transition: 0.15s;
		cursor: pointer;
		text-decoration: underline;
		font-size: 18px;
	}
	#language-switch span:hover {
		color: var(--secondary);
	}

	@media (max-width: 1100px) {
		h1 {
			margin-top: 50px;
		}
		#main-div {
			padding-left: 0px;
		}
		.projects-row {
			flex-direction: column;
		}
		.projects-row a {
			width: 100%;
		}

		.projects-row article {
			padding-right: 0;
			position: relative;
		}
		.projects-row article #image {
			max-width: 300px;
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
			padding-left: 10px;
			margin-top: 220px;
			position: absolute;
		}
		#hello {
			text-align: left;
			font-size: 20px;
		}
		#bio {
			font-size: 20px;
		}
		#my-work {
			margin-top: 140px;
		}
	}

	@media (max-width: 590px) {
		.projects-row article #image {
			position: absolute;
			top: 2px;
			right: 0;
			width: 90px;
		}
		h1 {
			font-size: 32px;
			line-height: normal;
		}
		#my-work {
			margin-top: 220px;
		}
		#right-main {
			margin-top: 180px;
		}
		.projects-row article {
			padding-left: 25px;
		}
	}

	@media (max-width: 590px) {
		#my-work {
			margin-top: 240px;
		}
		#right-main {
			margin-top: 240px;
		}
	}

	@media (max-width: 360px) {
		#bio {
			font-size: 18px;
		}
	}
</style>
