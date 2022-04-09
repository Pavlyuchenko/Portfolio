<script>
	import ImageLoader from "../../../components/ImageLoader.svelte";
	import ImageShowcase from "../../../components/ImageShowcase.svelte";
	import Heading1 from "../../../components/Heading1.svelte";
	import TextBlock from "../../../components/TextBlock.svelte";
	import Bullet3 from "../../../components/Bullet3.svelte";
</script>

<svelte:head>
	<title>SIR Model | Michal Pavlíček</title>
</svelte:head>

<article>
	<div>
		<div>
			<p id="date">bře. 2020 - dub. 2020</p>
			<h1>SIR Model</h1>
			<p id="description">
				Javascript animace simulující nejjednoduší model průběhu
				epidemie.
			</p>
		</div>
		<div id="image">
			<img
				src="https://ik.imagekit.io/velkadomu/sir_model_KuiE9xyZA.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504368913"
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
							src="js.png"
							alt="Javascript logo"
							title="Javascript"
						/>
						<img
							src="canvas.png"
							alt="HTML5 Canvas logo"
							title="Canvas"
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
					<p class="project-info-value" id="interval">1 měsíc</p>
				</div>
			</div>
		</div>
	</div>

	<div id="the-story">
		<div id="alert">
			<span id="excl-mark">!</span>
			<span>
				Tento projekt sloužil k naučení nové technologie. Nejde proto o
				úžasný projekt, ale spíše malou rychlovku, kterou jsem vytvořil
				k pochopení &lt;canvas&gt;.
				<a href="/project/velka-domu">Můj nejnovější projekt.</a>
			</span>
		</div>
		<h3>Prolog</h3>
		<p>
			<a
				href="https://codepen.io/Pavlyuchenko/pen/bGaMYgr"
				target="_blank"
			>
				Demo projektu.
			</a>
			<br />
			V březnu roku 2020 začala celosvětová epidemie Covid-19 a já se společně
			se všemi mými vrstevníky ocitl ze dne na den doma místo školy, téměř
			bez jakýchkoliv požadavků. Zpočátku jsem zažíval nadšení z prvních prázdnin
			tohoto druhu v historii a epidemiologická situace se prozatím vyvíjela
			poměrně klidně. V této době jeden z nejznámějších vzdělávacích Youtuberů
			<a href="https://www.youtube.com/c/3blue1brown" target="_blank">
				3Blue1Brown
			</a>
			vydal
			<a href="https://youtu.be/gxAaO2rsdIs" target="_blank">video</a>, ve
			kterém popisoval nejjednodušší epidemiologický model. Ten mě
			inspiroval k vytvoření vlastní programovatelné verze, díky které
			bych se doučil Vanilla Javascript a naučil se pokročilejší animace
			pomocí &lt;canvas&gt;.
		</p>
		<div id="intro-flex" class="flex">
			<div class="flex-child-left">
				<h3>Problém</h3>
				<p class="left-text">
					Vytvořit podle video předlohy jednoduchou simulaci epidemie
					koronaviru a překonat prokrastinaci, jelikož mám ve svých
					rukách téměř neomezené množství času.
				</p>
			</div>
			<div class="flex-child-right">
				<h3>Výsledek</h3>
				<p class="right-text">
					Naučil jsem se používat &lt;canvas&gt; a vytvořil zajímavou
					aplikaci poměrně reálně reflektující opravdový vývoj
					pandemie.
				</p>
			</div>
		</div>

		<Heading1
			description="Simulace pandemie"
			heading="Použití SIR modelu"
		/>
		<TextBlock
			text="Projekt používá k simulaci nejjednodušší epidemiologický model, tzv. SIR model. Jeho princip je poměrně jednoduchý a jasný:"
		/>
		<TextBlock
			text="V simulaci se v pomyslném 'městě' pohybují lidé, kteří nepřekračují jeho hranice. Tito lidé se mohou nacházet ve třech různých stavech:"
		/>

		<Bullet3
			points={[
				{
					text: "Zdravý",
					image: "blue.png",
					content: "",
				},
				{
					text: "Nakažený",
					image: "red.png",
					content: "",
				},
				{
					text: "Vyléčený/mrtvý",
					image: "grey.png",
					content: "",
				},
			]}
		/>
		<TextBlock
			text="Každý nakažený má kolem sebe neviditelný kruh. Když do něj vstoupí zdravý jedinec, tak má určitou šanci nakazit se také. Po nějakém čase přestane být jedinec infekční."
		/>

		<ImageLoader
			path="https://ik.imagekit.io/velkadomu/sir_VBf0dO0NC.gif?ik-sdk-version=javascript-1.4.3&updatedAt=1649504401287"
			alt="VFB"
			description="Krátká ukázka animace"
		/>

		<TextBlock
			text="Canvas funguje na principu neustálého přepisování celé plochy. Při každém framu se celá oblast vymaže a vytvoří se noví 'občané' o kousek přemístění. Při tom se také spočítá jejich vzájemná vzdálenost, případně když se zdravý člověk přiblíží nakaženému, pak se může podle určené pravděpodobnosti také nakazit."
		/>

		<Heading1
			description="Poučení"
			heading="Jakých chyb jsem se dopustil?"
		/>
		<Bullet3
			points={[
				{
					text: "Málo refaktorizace",
					image: "refactor.png",
					content:
						"Kód projektu nestojí na pevných základech a rozhodně by si zasloužil úpravu kódu, aby se stal přehlednějším a robustnějším",
				},
				{
					text: "Učení se za běhu",
					image: "book.png",
					content:
						"K získání zkušeností je tento přístup tím snad nejlepším, ale nevede k nejlepším výsledkům.",
				},
				{
					text: "Nepromyšlení složitosti",
					image: "settings.png",
					content:
						"Několik stovek pohybujících se kuliček není úplně každodenní chléb pro procesor, což jsem si na začátku neuvědomil a nepřišel s lepším algoritmem.",
				},
			]}
		/>

		<h3 class="epilogue">Epilog</h3>
		<p>
			Díky tomuto projektu jsem pochopil, jak funguje HTML tag canvas a
			celkově animace na webových stránkách. Tyto cenné zkušenosti jsem
			později využil v dalších projektech, kde jsem je použil na užitečnou
			věc, nejen k projektu sloužícímu k učení.
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
