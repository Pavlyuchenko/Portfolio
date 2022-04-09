<script>
	import ImageLoader from "../../../components/ImageLoader.svelte";
	import Heading1 from "../../../components/Heading1.svelte";
	import TextBlock from "../../../components/TextBlock.svelte";
</script>

<article>
	<div>
		<div>
			<p id="date">srpen 2021</p>
			<h1>Slibotechny</h1>
			<p id="description">
				Hlídač slibů politických stran v České republice.
			</p>
		</div>
		<div id="image">
			<img
				src="Slibotechny_preview.png"
				alt="Hlavní obrázek Slibotechny"
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
							src="python.png"
							alt="Python logo"
							title="Python"
						/>
						<img
							src="svelte.png"
							alt="Svelte logo"
							title="Svelte"
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
		<h3>Prolog</h3>
		<p>
			V létě roku 2021 jsem se ocitl ve velice mladém a ambiciózním týmu
			plném lidí zajímajících se o politiku. Společně jsme si všimli
			obrovské polarizace české společnosti, která mnohdy hlásala naprosto
			odlišné fakta. Problémem však bylo, že nikdo nemohl jednoznačně
			říci, kdo má vlastně pravdu? Proto jsme se rozhodli to změnit.
			Slibotechny si dávají za cíl zorientovat se ve slibech politických
			stran a zároveň kontrolovat, která strana ve skutečnosti dodrží to,
			co ve svých programech slíbí.
		</p>
		<div id="intro-flex" class="flex">
			<div class="flex-child-left">
				<h3>Problém</h3>
				<p class="left-text">
					Vytvořit dvě webové aplikace: jednu pro adminy, kteří
					potřebují jednoduše přidávat a upravovat body programu,
					druhou pro běžné uživatele s důrazem na přehlednost a
					jednoduchost.
				</p>
			</div>
			<div class="flex-child-right">
				<h3>Výsledek</h3>
				<p class="right-text">
					Výsledkem byla kvalitní stránka s důrazem na preciznost a co
					nejlepší možnou přehlednost. Responsibilita je nezbytnou
					samozřejmostí společně s líbivým designem a jednoduchostí
					ovládání.
				</p>
			</div>
		</div>

		<Heading1 description="Plánování" heading="Jasná představa" />
		<TextBlock
			text="Když jsem se do týmu dostal, byla již jasná přibližná představa o projektu stejně jako hrubý design stránky, takže na mě bylo dotáhnout tento design a pak jen vše splnit přesně podle požadavků. To pro mě bylo úplnou novinkou, protože jsem ve své dosavadní práci vymýšlel vše od A do Z já sám. Nyní jsem byl součástí zkušeného týmu, který na mě měl jasné požadavky."
		/>
		<TextBlock
			text="Po chvíli designování a upravování jsem dospěl k téměř finálnímu designu, přičemž jsem mu dodal šmrnc zajímavým tečkovaným pozadím. Spolupracovníkům se návrh líbil, takže jsem se brzy mohl dostat k hlavní části: k programování."
		/>
		<ImageLoader
			path="slibotechny_main_design.png"
			alt="Slibotechny hlavní design"
			description="První a konečný design hlavního zobrazení strany."
		/>

		<Heading1
			description="Programování"
			heading="Co je technicky zajímavé?"
		/>
		<TextBlock
			text="Backend tohoto projektu neobsahuje žádné vymoženosti, jde o pouhý CRUD s SQL databází. Na Frontendu však lze najít několik zajímavých rozhodnutí. Zaprvé jsem se rozhodl pro jednostránkovou aplikaci, přičemž vůbec nedochází k reloadům ze serveru. To má samozřejmě svůj důvod."
		/>
		<TextBlock
			text="Při vstupu uživatele na stránku se nestahují žádná data z BE, aby se co nejvíce snížil loading time. Uživatel pak musí zvolit nějakou politickou stranu, čímž se dostane na výběr kategorií. Jakmile přejede myší přes nějakou kategorii, tak se pošle request na BE, který vrátí přesně ta data, která si uživatel vyžádal a uloži je do paměti pro případné budoucí využití. Tento přístup co nejvíce minimalizuje stahování dat."
		/>
		<ImageLoader
			path="slibotechny_kategorie.png"
			alt="Výběr kategorie"
			description="Výběr katogorie slibu. Při hoveru se stahují data a ukládají se do společné paměti."
		/>

		<hr />

		<h3 class="epilogue">Epilog</h3>
		<p>
			Ve výsledku se projekt rozhodně povedl. Jak stránka pro desktop, tak
			i pro mobilní telefony vypadají skvěle a jsou uživatelsky přívětivé.
			Díky použití frameworku Sapper jsem zařídil dobrou SEO stránky.
			Jediný problém, se kterým je možné se v budoucnu setkat je fakt, že
			běžní uživatelé nemusí být zvyklí na používání stránky bez navigace
			a bez historie.
		</p>
		<h3 class="epilogue">Ponaučení</h3>
		<div class="flex " id="epilogue-div">
			<div class="flex-child-left">
				<div class="lesson-title">Pořádně promýšlej svá rozhodnutí</div>
				<p>
					Když jsem se rozhodl pro strukturu stránky tak, jak nyní je,
					neměl jsem úplně promyšlená všechna pro a proti, která to s
					sebou přináší. Na jednu stranu jsem získal plusové body ve
					výkonu, ale pár jich ztratil v UX. Až čas ukáže, zda jsem se
					rozhodl správně, což rozhodně správně není.
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
