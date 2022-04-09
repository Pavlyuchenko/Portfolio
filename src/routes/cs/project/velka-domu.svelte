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
			<p id="date">lis. 2020 - úno. 2021</p>
			<h1>VelkáDomů.cz</h1>
			<p id="description">
				CMS systém, front-end stránka a CRUD dazabáze pro ambiciózní
				fotbalový portál
			</p>
		</div>
		<div id="image">
			<img
				src="velkadomu2.png"
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
					<p class="project-info-value" id="interval">3 měsíce</p>
				</div>
			</div>
		</div>
	</div>

	<div id="the-story">
		<h3>Prolog</h3>
		<p>
			Začátkem listopadu 2020 jsem se spojil se svým spolužákem, abychom
			vytvořili webovou stránku, kde budeme moct prezentovat naše vlastní
			fotbalové zpravodajství. Mou starostí byla technická stránka,
			zatímco jeho práce zahrnovala především marketing a získání
			redaktorů. Hlavním cílem bylo získat početné čtenářské publikum, pro
			něž bychom byli hlavním zdrojem fotbalových novinek, získat cenné
			zkušenosti z oblasti podnikání a vyzkoušet si práci v týmu.
		</p>
		<div id="intro-flex" class="flex">
			<div class="flex-child-left">
				<h3>Problém</h3>
				<p class="left-text">
					Mým úkolem bylo vytvořit webovou aplikaci od píky včetně
					designu, back-endu a front-endu. Programoval jsem dvě verze,
					jednu pro běžného čtenáře, druhou pro redaktory, což
					zahrnuje také tvorbu redakčního systému a
					<a
						href="/showcase/text-editor"
						style="text-decoration: underline; cursor: pointer;"
						target="_blank"
					>
						textového procesoru
					</a>. Responsivita obou verzí byla samozřejmostí.
				</p>
			</div>
			<div class="flex-child-right">
				<h3>Výsledek</h3>
				<p class="right-text">
					Během čtyř měsíců jsem dodal plně funkční responzivní
					webovou aplikaci optimalizovanou pro SEO včetně rozhraní pro
					redaktory a pokročilého textového editoru.
				</p>
			</div>
		</div>

		<Heading1
			description="Vzhled projektu"
			heading="Bez designu nejsou koláče"
		/>
		<TextBlock
			text="Prvním krokem bylo vytvoření designu a ujasnění všech funkcí našeho projektu. Přednostní vytvoření designu skýtá mnoho výhod, především jsme mohli společně diskutovat nad požadovanou vizuální stránkou a bezbolestně dopracovat detaily. Po pár dnech jsme došli k prvnímu vzhledu naší stránky, který vypadal následovně:"
		/>

		<ImageLoader
			path="first_design.png"
			alt="VFB"
			description="První verze designu VelkáDomů.cz"
		/>

		<TextBlock
			text="Tato verze sice vypadá na první pohled přívětivě, čtenáře však hned z počátku zahltí mnoho výrazných barev a grafických prvků. Kromě tří primárních článků tento prototyp postrádá vizuální hierarchii a mate čtenáře. Proto jsme se rozhodli vytvořit druhou verzi, která vizuální hierarchii vylepšuje, přičemž přináší přívětivý a konzistentní vzhled:"
		/>
		<ImageLoader
			path="new_design.png"
			alt="VFB"
			description="Finální verze designu"
		/>

		<TextBlock
			text="Nová verze čtenáře nezahlcuje, jelikož při příchodu na stránku zobrazuje pouze čtyři ručně vybrané nejrelevantnější články. Až níže se zobrazí dodatečné funkce společně s dalšími aktuálními články. Po konzultaci s dalšími lidmi jsme se rozhodli realizovat druhou verzi kvůli následujícím třem bodům:"
		/>
		<Bullet3
			points={[
				{
					text: "Vizuální hierarchie",
					image: "crown.png",
					content:
						"Stránka má jasně dané nejvýraznější prvky, díky čemuž uživatel neustále ví, kam se má dívat.",
				},
				{
					text: "Unikátnost",
					image: "unique.png",
					content:
						"Design stránky je zapamatovatelný a lehce uživateli utkví v paměti jeho přednostní prvky.",
				},
				{
					text: "Jednoduchost",
					image: "simple.png",
					content:
						"Navzdory předchozím bodům, zůstává design přehledný bez zbytečně křiklavých prvků.",
				},
			]}
		/>

		<Heading1
			description="Použité technologie"
			heading="Tech stack našeho projektu"
		/>
		<TextBlock
			text="Po zpracování vizuální stránky přišlo na řadu samotné programování. Pro tento projekt jsem zvolil následující technologie:"
		/>
		<Bullet3
			points={[
				{
					text: "Backend - Flask",
					image: "flask.png",
					content:
						"Framework Flask jsem zvolil kvůli své znalosti Pythonu a jednoduchosti tohoto frameworku.",
				},
				{
					text: "Frontend - Sapper",
					image: "sapper.png",
					content:
						"Sapper je server-rendered framework Svelte, což zaručuje jak dobré SEO, tak rychlost vývoje.",
				},
				{
					text: "Databáze - SQLAlchemy",
					image: "sqlalchemy.png",
					content:
						"SQLAlchemy je dobře přizpůsoben pro práci s Flaskem, takže je i přes jeho občasné nedostatky nejlepší volbou.",
				},
			]}
		/>

		<Heading1
			description="Prostředí pro redaktory"
			heading="Co uživatel nevidí, to srdce nebolí"
			id="texteditor"
		/>

		<ImageLoader
			path="text_editor.png"
			alt="Test"
			description="Textový editor naprogramovaný pro redakční systém"
		/>

		<TextBlock
			text="Nejprve přišlo na řadu programování redaktorského prostředí. Tento proces se rozdělil na dva primární problémy: textový editor a správa článků. Při programování textového editoru jsem se mohl rozhodnout pro klasické out-of-the-box WYSIWYG řešení. Ale jelikož mezi cíle projektu patřila také experimentace, rozhodl jsem se pro vytvoření vlastního block-based editoru, jehož popularita je v poslední době na vzestupu. Jeho základní demo lze najít <a href='/showcase/text-editor' target='_blank'>zde</a>."
		/>

		<ImageLoader
			path="TextEditor.gif"
			alt="Test"
			description="Textový editor naprogramovaný pro redakční systém"
		/>

		<TextBlock
			text="Editor ve finální verzi automaticky ukládá práci redaktorů, a po jejím dokončení je tento text v backendu transformován do HTML kódu. Jakmile byl editor dokončen, bylo již poměrně triviální dodat systému pěkný kabátek, dotvořit tabulku se všemi články a naprogramovat dodatečné funkce."
		/>
		<TextBlock
			text="<i style='font-size: 17px;'>(Ve zkratce tyto dodatečné funkce představují: redakční systém disponuje dvěma rolemi pro redaktory: běžným adminem a 'superadminem' pro hlavní členy týmu. Admin může pouze psát články a 'rychlovky' a dívat se na své statistiky, zatímco superadmin vidí statistiky všech redaktorů a může nastavovat, které články jsou zobrazovány prioritně na hlavní stránce.)</i>"
		/>
		<TextBlock
			text="Jelikož toto rozhrání není zásadní pro SEO a běžný uživatel tyto stránky nevidí, před vzhledem tak dostávají přednost ostatní priority. Proto jsem se při programování redakčního systému soustředil především na tyto aspekty:"
		/>
		<Bullet3
			points={[
				{
					text: "Jednoduchost",
					image: "simple.png",
					content:
						"Redaktor musí mít na jasno, kde se co nachází, aby se mohl soustředit jen na to nejdůležitější.",
				},
				{
					text: "Přehlednost",
					image: "clarity.png",
					content:
						"Obsah stránek nesmí být přeplněný, aby redaktor nebyl zahlcen mnoha možnostmi.",
				},
				{
					text: "Bezchybnost",
					image: "flawless.png",
					content:
						"Redaktoři nejsou programátoři. Pokud se něco pokazí, nemusí jim být jasné, jak problém vyřešit. Proto je nutné klást důraz na precizní systém.",
				},
			]}
		/>
		<ImageShowcase
			imgs={[
				{ path: "admin.png", alt: "VFB" },
				{ path: "title_image.png", alt: "VFB" },
				{ path: "cms.png", alt: "VFB" },
				{ path: "rychlovky.png", alt: "VFB" },
				{ path: "nova_rychlovka.png", alt: "VFB" },
			]}
		/>

		<Heading1
			description="Prostředí pro čtenáře"
			heading="Náš čtenář, náš pán"
		/>
		<TextBlock
			text="Narozdíl od redakčního systému musí u čtenářského zážitku být naopak kladen zásadní důraz na grafickou atraktivitu stránky. Kromě toho v tento moment přišlo na řadu spojování všeho dohromady. Výsledný systém nakonec funguje na tomto principu:"
		/>

		<ImageLoader
			path="scheme.png"
			alt="Test"
			description="Na jakém principu funguje VelkáDomů.cz?"
		/>

		<TextBlock
			text="V průběhu programování prostředí pro čtenáře docházelo k neustálému testování s novými spolupracovníky na projektu napříč různými platformami a jejich zpětné vazbě. V tomto finálním kroku však šlo pouze o získání dat ze serveru a zobrazení je na stránce pomocí HTML a CSS za použití existujícího designového rámce. Tento krok také zahrnoval vytvoření vlastního přihlašovacího systému kvůli hlasování v anketách a zařízení responzivity všech stránek. Výsledek lze vidět na této stránce <a href='https://velkadomu-sapper.vercel.app/' target='_blank'>velkadomu.cz</a> (vzorový účet: test@test.test, heslo: Testing123) nebo na následujících obrázcích:"
		/>
		<ImageShowcase
			imgs={[
				{ path: "landing_velka_domu.png", alt: "VFB" },
				{ path: "nejnovejsi_clanky_velka_domu.png", alt: "VFB" },
				{ path: "clanek_velka_domu.png", alt: "VFB" },
				{
					path: "anketa1.gif",
					alt: "VFB",
					altPath: "anketa.png",
				},
				{ path: "kalendar.png", alt: "VFB" },
				{ path: "mobile_velka_domu.png", alt: "VFB" },
			]}
		/>
		<ImageLoader
			path="landing_mobile.gif"
			alt="Test"
			description="Hlavní mobilní stránka VelkáDomů.cz"
			width="30"
		/>

		<h3 class="epilogue">Epilog</h3>
		<p>
			Být jediným fullstack vývojářem celého projektu občas není úplně
			nejjednoduší. Poprvé jsem si vyzkoušel, jaké to je, když na mé práci
			závisí několik dalších lidí, nesmím selhat a zároveň musím dodržet
			deadline. I když jsem na celý vývojový proces byl sám, dokázal jsem
			bez větších problému vytvořit kvalitní aplikaci a získal jsem
			zkušenosti ze všech koutů vývoje.
		</p>
		<h3 class="epilogue">Ponaučení</h3>
		<div class="flex " id="epilogue-div">
			<div class="flex-child-left">
				<div class="lesson-title">Dvakrát komunikuj, jednou řež</div>
				<p>
					V průběhu projektu jsme průběh konzultovali především ve
					dvou lidech a již v tak malém počtu docházelo k občasným
					nedorozuměním, což pro mě bylo oproti individuálním
					projektům novinkou. Naučil jsem se, že první si musím být
					stoprocentně jistý tím, co se po mně chce, a až pak můžu
					začit pracovat.
				</p>
			</div>
			<div class="flex-child-right">
				<div class="lesson-title">Nepředpokládej, ale zjišťuj</div>
				<p>
					Projekt takových rozměrů jsem tvořil poprvé, proto bylo
					mnoho funckí experimentací a zjišťování, jak věcí fungují.
					Od začátku jsem předpokládal, že až všechno dodělám, nakonec
					přidám sdílení na sociální sítě. Pak jsem ale zjistil, že
					sdílení nefunguje na frontend aplikacích, nýbrž jen na
					stránkách renderovaných v backendu. Na jednu stranu jsem
					konečně pochopil, jaký je mezi těmito způsoby rozdíl, na
					stranu druhou jsem musel strávit pár hodin přepisováním
					kódu.
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

	#main-image {
		border-radius: 5px 5px 0 0;
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
