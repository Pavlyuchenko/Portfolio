<script>
	import ImageLoader from "../../../components/ImageLoader.svelte";
	import ImageShowcase from "../../../components/ImageShowcase.svelte";
	import Heading1 from "../../../components/Heading1.svelte";
	import TextBlock from "../../../components/TextBlock.svelte";
	import Bullet3 from "../../../components/Bullet3.svelte";
</script>

<svelte:head>
	<title>VelkáDomů.cz | Michal Pavlíček</title>
</svelte:head>

<article>
	<div>
		<div>
			<p id="date">dub. 2019 - čvc. 2019</p>
			<h1>Projekt Jídelna</h1>
			<p id="description">
				Můj první velký projekt sestávající z backendu a CRUD databáze.
			</p>
		</div>
		<div id="image">
			<img
				src="pj_main.png"
				alt="VelkáDomů hlavní obrázek"
				id="main-image"
			/>

			<div id="project-info">
				<div>
					<p class="project-info-title">Má role</p>
					<p class="project-info-value" id="role">Všechny</p>
				</div>
				<div>
					<p class="project-info-title">Technologie</p>
					<p class="project-info-value" id="tech">
						<img
							src="python.png"
							alt="Python logo"
							title="Python"
						/>
						<img
							src="jquery.png"
							alt="jQuery logo"
							title="jQuery"
						/>
						<img
							loading="lazy"
							src="figma.png"
							alt="Figma logo"
							title="Figma"
						/>
					</p>
				</div>
				<div>
					<p class="project-info-title">Interval</p>
					<p class="project-info-value" id="interval">4 měsíce</p>
				</div>
			</div>
		</div>
	</div>

	<div id="the-story">
		<div id="alert">
			<span id="excl-mark">!</span>
			<span>
				Tento projekt je mým prvním větším projektem. Spíše než o
				vytvoření použitelné aplikace mi šlo především o naučení se
				základům tvoření webových stránek. Ber jej proto s rezervou,
				prosím.
				<a href="/project/velka-domu">Můj nejnovější projekt.</a>
			</span>
		</div>
		<h3>Prolog</h3>
		<p>
			Při prezentaci potenciálních nápadů pro podnikání v hodině zeměpisu
			jeden z mých spolužáků přišel s užitečným nápadem. Spočíval v tom,
			že by bylo možné při výběru obědů ve školní jídelně zvažovat svůj
			výběr také podle obrázků. Rok poté jsem se naučil programovat a
			společně s dvěma spolužačkami jsme se rozhodli do tohoto projektu
			pustit. Já jsem byl v programování úplný začátečník a toto byl můj
			premiérový větší projekt, takže spíš než výsledek bylo důležité
			získání zkušeností.
		</p>
		<div id="intro-flex" class="flex">
			<div class="flex-child-left">
				<h3>Problém</h3>
				<p class="left-text">
					Vytvořit webovou stránku, na které bude možné v průběhu roku
					přidávat do databáze fotky jídel ze školní jídelny a po
					několika měsících, až bude záznamů hodně, tyto fotky
					zobrazovat u podobných jídel (s podobnými klíčovými slovy v
					názvu) společně s hodnocením dalších stravníků.
				</p>
			</div>
			<div class="flex-child-right">
				<h3>Výsledek</h3>
				<p class="right-text">
					Vytvořil jsem jednoduchou stránku v Python frameworku Flask
					umožňující mimo jiné založení účtu, přidávání fotek a
					recenzování jídel.
				</p>
			</div>
		</div>

		<Heading1
			description="První reálný projekt"
			heading="Sometimes you gotta run before you can walk"
		/>
		<TextBlock
			text="Tento projekt byl již od začátku nad moje tehdejší programovací síly. Ale jelikož se při učení řídím především heslem 'chybami se člověk učí', pustil jsem se do designování i programování rovnou po hlavě. Moje dovednosti v HTML a CSS byly v plenkách, stejně jako programování v Pythonu, vůbec nemluvě o Flasku ani designu. "
		/>
		<TextBlock
			text="Na začátku jsem poprvé v životě stáhl Figmu, se kterou jsem neměl pražádné zkušenosti, a co hůř, zkušenost jsem neměl ani s podobnými programy. Ale přesto mě designování stránky vtáhlo a brzy jsem přišel s několika návrhy, které však nepatří mezi klenoty umění:"
		/>
		<ImageShowcase
			imgs={[
				{ path: "https://ik.imagekit.io/velkadomu/pj_landing_jnqjiCmnS.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504364286", alt: "VFB" },
				{ path: "https://ik.imagekit.io/velkadomu/pj_landing_logged_dOkXgn2lE.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504367639", alt: "VFB" },
				{ path: "https://ik.imagekit.io/velkadomu/pj_register_m6X4Irc6r.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504364186", alt: "VFB" },
				{
					path: "https://ik.imagekit.io/velkadomu/pj_recenze_WFQ0L2tTPa.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504369163",
					alt: "VFB",
				},
				{
					path: "https://ik.imagekit.io/velkadomu/pj_vyber_O_gQcqnNuY.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504367076",
					alt: "VFB",
				},
			]}
		/>

		<Heading1
			description="Funkce stránky"
			heading="Nabytí nových zkušeností je prioritou"
		/>

		<TextBlock
			text="Kvůli mnoha problémům se projekt nikdy nedostal do běžného užívání, i přesto však byl zcela funkční. Hlavní stránka vypadá poměrně dobře, celkový design sice nepatří mezi ty nejlepší, ale pro školní stránku je dostačující. Backend uměl stáhnout data ze serveru jídelny, která nedisponovala API, zobrazit správné obrázky z předchozích obědů, hodnotit je, přidávat komentáře, emoji, a poté dokonce taky 'naklikat' uživateli jeho vybrané obědy na stránkách jídelny, i když tato funkce zabrala přes 60 sekund (byla prováděna ve front-endu, což je samozřejmě problematické). "
		/>
		<TextBlock
			text="Každopádně stránka byla úspěšně dokončena a některé funkce bych označil za velmi povedené, kromě principu přidávání obědů také jejich recenzování:"
		/>

		<ImageLoader
			path="https://ik.imagekit.io/velkadomu/pj_rating_bpnLyxx3w.gif?ik-sdk-version=javascript-1.4.3&updatedAt=1649504381494"
			alt="VFB"
			description="Hodnocení obědů"
		/>

		<TextBlock
			text="Ve výsledku nejde o grandiózní a oslňující projekt, chtěl jsem však zdokumentovat a ukázat proces mého učení. "
		/>

		<Heading1
			description="Poučení"
			heading="Jakých chyb jsem se dopustil?"
		/>
		<Bullet3
			points={[
				{
					text: "Žádný plán",
					image: "plan.png",
					content:
						"Během programování jsem mnoho částí několikrát předělával kvůli absenci plánu.",
				},
				{
					text: "Nezkušenost s programováním",
					image: "prog.png",
					content:
						"I když jsem uměl programovat v Pythonu, stále jsem si v mnoha věcech nebyl jistý.",
				},
				{
					text: "Neznalost frameworku",
					image: "framework.png",
					content:
						"Flask jsem používal poprvé v životě, mnoho funkcí jsem se učil za chodu.",
				},
			]}
		/>

		<h3 class="epilogue">Epilog</h3>
		<p>
			Tento projekt řadím mezi své srdcové záležitosti. Nejde o žádný
			skvostný projekt. Právě naopak je tento projekt opravdu hnusný. Díky
			tomu vidím, jak dalekou cestu jsem v programování ušel a vidím na
			něm chyby, o kterých jsem v době jeho programování něměl žádné
			tušení.
		</p>
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

	#epilogue-div p {
		margin-top: 20px;
	}

	.flex .lesson-title {
		background-color: #cbcede;
		width: -moz-fit-content;
		width: fit-content;
		padding: 10px 18px;

		font-weight: 500;
		font-size: 18px;
	}

	#main-image {
		border-radius: 5px 5px 0 0;
	}

	#alert {
		background-color: #d64550;
		color: #ffffff;
		padding: 15px 17px;
		margin-top: -35px;
		margin-bottom: 40px;
		border-radius: 5px;
		display: flex;
		font-size: 17px;
	}
	#alert #excl-mark {
		font-family: "Inter";
		font-size: 45px;
		line-height: 45px;
		font-weight: 600;
		margin-right: 15px;
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
