<script>
	import ImageLoader from "../../../components/ImageLoader.svelte";
	import ImageShowcase from "../../../components/ImageShowcase.svelte";
	import Heading1 from "../../../components/Heading1.svelte";
	import Heading2 from "../../../components/Heading2.svelte";
	import TextBlock from "../../../components/TextBlock.svelte";
	import Bullet3 from "../../../components/Bullet3.svelte";
</script>

<article>
	<div>
		<div>
			<p id="date">kvě- 2020 - čvn. 2020</p>
			<h1>Florbalový vánoční turnaj</h1>
			<p id="description">
				Webová aplikace pro každoroční sportovní akci podporující real
				time zobrazování výsledků.
			</p>
		</div>
		<div id="image">
			<img
				src="vfb_main.png"
				alt="Vánoční florbalový turnaj hlavní obrázek"
			/>

			<div id="project-info">
				<div>
					<p class="project-info-title">Má role</p>
					<p class="project-info-value" id="role">Full stack</p>
				</div>
				<div>
					<p class="project-info-title">Technologie</p>
					<p class="project-info-value" id="tech">
						<img
							loading="lazy"
							src="react.png"
							alt="React logo"
							title="React"
						/>
						<img
							src="python.png"
							alt="Python logo"
							title="Python"
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
					<p class="project-info-value" id="interval">3 měsíce</p>
				</div>
			</div>
		</div>
	</div>

	<div id="the-story">
		<h3>Prolog</h3>
		<p>
			Na Mendelově gymnáziu v Opavě se každoročně (s Covidovými
			přestávkami) koná Vánoční florbalový turnaj. Na něm se vždy utkávají
			žáci všech věků a pohlaví nejen mezi sebou, ale také se svými
			učiteli. Cílem tohoto projektu je této tradici dodat moderní háv v
			podobě webové aplikace zobrazující aktuální stav zápasů a pozici
			týmů v tabulce.
		</p>
		<div id="intro-flex" class="flex">
			<div class="flex-child-left">
				<h3>Problém</h3>
				<p class="left-text">
					Vytvořit jednoduchou, přehlednou a také responsivní stránku
					zobrazující aktuální stav celého turnaje.
				</p>
			</div>
			<div class="flex-child-right">
				<h3>Výsledek</h3>
				<p class="right-text">
					Vytvořil jsem efektivní real-time výsledkovou aplikaci pro
					školní turnaj, která zvládne updatovat dva zápasy najednou.
				</p>
			</div>
		</div>

		<Heading1
			description="Vtáhnout uživatele do děje"
			heading="Úvodní stránka"
		/>
		<TextBlock
			text="První dojem je téměř všechno. Úvodní stránka projektu právě z tohoto důvodu musí uživatel zaujmout co nejvíce to jde. Proto jsem se rozhodl před uživatele hned ze začátku postavit rozhodnutí, které však vypadá pěkně a působí elegantně a profesionálně. "
		/>
		<TextBlock
			text="Uživatel si na startu vybere tým, kterému fandí. Toto rozhodnutí se poté projeví tak, že mu budou chodit notifikace o následujících zápasech tohoto týmu a jejich postavení v tabulce."
		/>
		<ImageLoader
			path="VFB_team_choice.gif"
			alt="Výběr týmu"
			description="Reaktivní výběr týmu na úvodní stránce."
		/>

		<Heading1
			description="Uživatelské prostředí"
			heading="Prezentování informací uživateli"
		/>
		<TextBlock
			text="Po výběru se uživatel octne na hlavním dashboardu mé stránky. Ten sestává z navigace, detailech zrovna hrajícího zápasu, nejbližších zápasů a tabulky hrající skupiny. Jednoduše vše, co by uživatel mohl při vstupu na stránku nejdříve potřebovat."
		/>
		<TextBlock
			text="Vše se snaží působit jednoduše a přehledně, ale zároveň graficky příjemně, aby uživatel na mou stránku nezanevřel kvůli designovým prvkům."
		/>
		<ImageLoader
			path="vfb_landing.png"
			alt="Dashboard"
			description="Primární dashboard s nejnutnějšími informacemi."
		/>

		<Heading1
			description="Adminovské rozhraní"
			heading="Jak se do systému dostávají informace?"
		/>
		<ImageLoader
			path="vfb_showcase.gif"
			alt="Ukázka real-time updatování informací"
			description="Updatování informací z Backendu u uživatele."
		/>
		<TextBlock
			text="Základem podobné stránky samozřejmě musí být také zadávání výsledků do databáze. Tuto funkcionality jsem se rozhodl spojit s časomírou a tabulí, protože je nutné během zápasů týmům také zobrazovat momentální stav. Takže v průběhu zápasů se na monitoru zobrazuje stav a čas, a po konci zápasu se vše instantně zapíše do databáze."
		/>
		<TextBlock
			text="Třešničkou na dortu je, že se informace přenášejí ke klientům v reálném čase, takže mají o zápasech přehled, i když se zrovna nenachází v tělocvičně."
		/>
		<ImageLoader
			path="VFB_real_time.gif"
			alt="Real time ukázka"
			description="Zobrazování informací v reálném čase."
		/>

		<Heading1
			description="Dodatečné funkce"
			heading="Responsivita a další funkce"
		/>
		<TextBlock
			text="Stránka samozřejmě nabízí další rozšiřující funkce, jako například detail týmu nebo dokonce zápasu, kde by šel vidět čas vstřeleného gólu a trestné minuty. Také je samozřejmostí rozpis všech nadcházajících zápasů nebo tabulky všech skupin."
		/>
		<TextBlock
			text="Krom toho jsem měl na mysli také responzivitu stránky, neboť její hlavní užití bylo zamýšleno na mobilních telefonech, jelikož to je v podstatě to jediné zařízení, které studenti ve škole používají."
		/>
		ImageShowcase imgs={[
			{ path: "vfb_detail.png", alt: "Detail týmu" },
			{ path: "vfb_rozpis.png", alt: "Rozpis zápasů" },
			{ path: "vfb_mobile.png", alt: "Mobilní verze" },
		]}
		/>

		<hr />

		<h3 class="epilogue">Epilog</h3>
		<div>
			<p>
				Závěrem musím zmínit, že jde o opravdu povedenou aplikaci. Vše
				působí moderně a plynule a navíc působí graficky pěkně. Nabízí
				uživateli všechny potřebné informace v přehledné formě a
				umožňuje týmům najít jak své následující zápasy, tak taky jejich
				umístění v tabulce.
			</p>
		</div>
		<h3 class="epilogue">Ponaučení</h3>
		<div class="flex " id="epilogue-div">
			<div class="flex-child-left">
				<div class="lesson-title">Počítej s nemožným</div>
				<p>
					Stránku jsem programoval s dostatečným předstihem v létě
					2020, abych ji bez potíží stihl dodat o Vánocích téhož roku.
					Nesmírně jsem se do tvorby zabral a programování mi spolklo
					téměř všechen čas. Pak však přišla celosvětová pandemie a
					celá práce se posunula o dva roky.
				</p>
			</div>
			<div class="flex-child-right">
				<div class="lesson-title">Mobile first</div>
				<p>
					Stránku jsem nejprve programoval především pro desktop, i
					když jsem věděl, že její uživatelé ji budou v drtivé většině
					používat na mobilu a ztratil jsem tak hodně času dolazováním
					detailů pro desktop, i když jsem se měl zaměřit spíše na
					mobilní platformu.
				</p>
			</div>
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
