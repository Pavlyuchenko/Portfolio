<script>
	import Heading1 from "../../../components/Heading1.svelte";
	import TextBlock from "../../../components/TextBlock.svelte";
</script>

<article>
	<div>
		<div>
			<p id="date">září. 2021 - prosinec. 2021</p>
			<h1>Partners exekuce</h1>
			<p id="description">
				V mé první práci pro společnost Zauzoo jsem pracoval na projektu
				pro společnost nabízející finanční poradentství Partners a
				poprvé jsem měl možnost spolupracovat s ostatními programátory.
			</p>
		</div>
		<div id="image">
			<img
				loading="lazy"
				src="zauzoo_main.png"
				alt="Hlavní obrázek Zauzoo"
			/>

			<div id="project-info">
				<div>
					<p class="project-info-title">Má role</p>
					<p class="project-info-value" id="role">Front-end</p>
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
							src="mui.png"
							alt="Material UI logo"
							title="Material UI"
						/>
						<img
							src="gitlab.png"
							alt="Gitlab logo"
							title="Gitlab"
						/>
					</p>
				</div>
				<div>
					<p class="project-info-title">Interval</p>
					<p class="project-info-value" id="interval">4 měsíců</p>
				</div>
			</div>
		</div>
	</div>

	<div id="the-story">
		<h3>Prolog</h3>
		<p>
			Do projektu jsem se dostal v již poměrně pokročilé fázi, což pro mě
			byl celkem šok. Ještě nikdy jsem nemusel po ostatních programátorech
			číst kód, natož v takovém měřítku. K tomu jsem pracoval v Reactu,
			což nebyl framework, ve kterém bych byl úplně nejjistější, a navíc
			jsem musel používat Material UI, což pro mě byla také premiéra.
		</p>
		<div id="intro-flex" class="flex">
			<div class="flex-child-left">
				<h3>Problém</h3>
				<p class="left-text">
					Opravovat stávající code base a přidávat novou funkcionalitu
					na front-end projektu podle issues, které mi byly přiřazeny
					na Gitlabu.
				</p>
			</div>
			<div class="flex-child-right">
				<h3>Výsledek</h3>
				<p class="right-text">
					Úspěšně jsem vypracoval několik desítek issues, které byly
					schváleny ostatními členy týmu.
				</p>
			</div>
		</div>

		<Heading1
			description="První pracovní zkušenost"
			heading="Práce v Zauzoo"
		/>
		<TextBlock
			text="V září roku 2021 jsem se poprvé v životě stal zaměstnancem programovací společnosti. Nebyla to sice práce na plný úvazek, ale k opravdové práci už to nemá daleko. V mém prvním projektu jsem dostal možnost spolupracovat s dalším středoškolským studentem, se kterým jsme se ihned zkamarádili a pomáháme si navzájem i nyní, i když už spolu přímo nespolupracujeme. To pro mě bylo ohromné plus."
		/>
		<TextBlock
			text="V průběhu mé práce na projektu jsem si vyzkoušel mnoho věcí poprvé v životě. Poprvé jsem si vyzkoušel práci s Gitem  s několika spolupracovníky, naučil se několik nových technologií (například Material UI) a především komunikaci s dalšími programátory."
		/>

		<hr />

		<h3 class="epilogue">Epilog</h3>
		<p>
			Nejsem si úplně jistý, zda zde můžu mluvit a ukazovat tento projekt
			konkrétněji, takže jsem se rozhodl, že radši nebudu. Ale nutno říci,
			že mi tato zkušenost hodně rozšířila obzory a jsem velice rád, že
			jsem takovou příležitost dostal.
		</p>
		<h3 class="epilogue">Ponaučení</h3>
		<div class="flex " id="epilogue-div">
			<div class="flex-child-left">
				<div class="lesson-title">Hodně toho nevíš</div>
				<p>
					Na začátku jsem si myslel, že budu úkoly zvládat s naprostým
					přehledem. To se ale nestalo. Jen setup projektu na mém
					počítači mi dal zabrat, Material UI pro mě byl jako
					španělská vesnice a projekt byl již v hodně pokročilém
					stádiu, takže jsem byl zmatený a nevěděl, co kde hledat.
					Pořád je co se učit.
				</p>
			</div>
			<div class="flex-child-right">
				<div class="lesson-title">Neboj se zeptat</div>
				<p>
					Ještě pořád mám divný pocit, když se chci někoho zeptat na
					věc, kterou úplně nechápu nebo mi nefunguje. Každopádně jsem
					došel k závěru, že je mnohem lepší vypadat jako hlupák, než
					si o případnou pomoc neříct.
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
		width: 20px;
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
