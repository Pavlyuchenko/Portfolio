<section>
	<img src="profile_edited.png" alt="Me, myself and I" id="profile" />
	<div id="personal-info">
		<h3>About</h3>
		<hr />

		<h1>
			Ahoj, já jsem <span style="color: var(--primary);">Michal</span>
		</h1>
		<p id="main-desc">
			Jsem full-stack developer žijící v Opavě. Snažím se posouvat jako
			jako programátor i jako člověk, rád navazuji spojení s dalšími
			stejně smýšlejícími lidmi a užívám si řešení zajímavých a náročných
			problémů.
		</p>
		<p id="desc">
			Zrovna pracuji part-time jako front-end a test engineer v
			<a href="https://zauzoo.com" target="_blank">Zauzoo</a>. Vytvořil
			jsem jak back-end, tak i front-end pro projekty
			<a href="https://velkadomu-sapper.vercel.app" target="_blank">
				VelkáDomů.cz
			</a>
			a
			<a href="https://slibotechny.cz" target="_blank">Slibotechny</a>.
			Hlavní technologie, které používám k vytvoření nezapomenutelného
			webového zážitku jsou Flask, Svelte a React.
		</p>
		<p id="desc">
			Až do konce května 2022 studuji na Mendelově gymnáziu v Opavě a po
			ukončení studia se chci vydat na studium univerzity v Leidenu,
			konkrétně na obor Data Science & Artificial Intelligence hlavně
			proto, že mě tento obor nesmírně zajímá, ale také mi to připadá jako
			logický odrazový můstek pro mou další IT kariéru.
		</p>
		<p id="desc">
			Když zrovna neprogramuji, nedesignuji nebo neřeším alogritmické
			problémy, najdete mě nejspíš na fotbalovém hřišti, nebo jak se dívám
			na sci-fi seriály, čtu (zase hlavně sci-fi) knihy, investuji do
			akcií nebo krypta nebo trávím čas s kamarády.
		</p>
		<p id="desc">
			Usiluji o to, abych byl člověk s otevřenou myslí připravený pomoci
			mým spolupracovníkům, ochoten naučit se rychle rozvíjející se
			technologie, sečtělý a fyzicky zdatný.
		</p>
		<p id="desc">
			Mezi mé největší programovací úspěchy patří získání práce v Zauzoo,
			dosáhnutí 20. místa v ústředním kole Matematické olympiády kategorie
			P a taktéž zisk 20. místa v programovací soutěži Kasiopea.
		</p>
	</div>
</section>
<div id="skills-wrapper">
	<h3>Dovednosti</h3>
	<hr />
	<div class="skills">
		<div class="grid-column">
			<p>Python</p>
			<p>Flask</p>
			<p>SQL Alchemy</p>
			<p>React</p>
			<p>HTML & CSS</p>
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
		</div>
	</div>
</div>
<div id="skills-wrapper">
	<h3>Úspěchy</h3>
	<hr />
	<div class="skills">
		<div class="grid-column">
			<p>20. místo, ústřední kolo</p>
			<p style="font-weight: 400;">Matematická olympiáda, kat. P</p>
		</div>
		<div class="grid-column">
			<p>20. místo, národní kolo</p>
			<p style="font-weight: 400;">Kasiopea</p>
		</div>
		<div class="grid-column">
			<p>1. místo, národní kolo</p>
			<p style="font-weight: 400;">High School Busines Challenge</p>
		</div>
	</div>
</div>

<style>
	section {
		margin-top: 50px;
		padding: 0px calc((100% - 73rem) / 2) 0px calc((100% - 73rem) / 2);

		display: flex;
		justify-content: space-between;
	}
	#profile {
		width: 40%;
	}
	#personal-info {
		width: 57%;
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
		padding: 0px calc((100% - 73rem) / 2) 0px calc((100% - 73rem) / 2);
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

	@media (max-width: 1250px) {
		section {
			display: block;
		}
		#profile {
			margin-left: 50%;
			transform: translateX(-50%);
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
	}
</style>
