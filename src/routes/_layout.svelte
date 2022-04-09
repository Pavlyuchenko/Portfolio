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
						src="michal_pavlicek.webp"
						alt="Michal Pavlíček foto"
						width="64"
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
						Webdesigner
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
							src="uk.svg"
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
					src="michal_pavlicek.webp"
					alt="Michal Pavlíček foto"
					width="32"
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
			<a href="/">Portfolio</a>
			<a href="/blog">Blog</a>
			<a href="/omne">O mně</a>
			<hr id="mobile-hr" />
		</div>
		<slot />

		<footer>
			<div id="text">
				<h2>Pojďme něco vytvořit společně!</h2>
				<p>
					Máš nějaký zajímavý nápad, portřebuješ s něčím pomoct nebo
					se se mnou chceš spojit?
					<br />
					Pak se neboj napsat na mou emailovou adresu, rád se připojím
					i k menším projektům:
				</p>
				<br />
				<a
					href="https://mail.google.com/mail/u/0/?fs=1&to=michaelg.pavlicek@gmail.com&su=Chci s tebou spolupracovat!&tf=cm"
					target="_blank"
				>
					michaelg.pavlicek@gmail.com
				</a>
			</div>
		</footer>
	</main>
{/if}

<style>
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
		font-weight: 500;
		font-size: 1.5em;

		margin-bottom: 0px;
	}
	p {
		margin: 0;
		font-weight: 500;

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
		font-weight: 500;
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

	@media (max-width: 700px) {
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
