<script>
	import Heading1 from "../../../components/Heading1.svelte";
	import TextBlock from "../../../components/TextBlock.svelte";
</script>

<article>
	<div>
		<div>
			<p id="date">led. 2022 -</p>
			<h1>Testing Expobank</h1>
			<p id="description">
				Psal jsem testy pro velkou aplikaci internetového bankovnictví
				pomocí technologií Jasmine a KarmaJS.
			</p>
		</div>
		<div id="image">
			<img src="expobank_main.png" alt="Expobank logo" />

			<div id="project-info">
				<div>
					<p class="project-info-title">Má role</p>
					<p class="project-info-value" id="role">Tester</p>
				</div>
				<div>
					<p class="project-info-title">Technologie</p>
					<p class="project-info-value" id="tech">
						<img
							src="play.png"
							alt="Play Framework logo"
							title="Play Framework"
						/>
						<img
							src="jasmine.png"
							alt="Jasmine logo"
							title="Jasmine"
							width="21"
							height="21"
						/>
						<img
							src="karmajs.png"
							alt="KarmaJS logo"
							title="KarmaJS"
						/>
					</p>
				</div>
				<div>
					<p class="project-info-title">Interval</p>
					<p class="project-info-value" id="interval">3 měsíců</p>
				</div>
			</div>
		</div>
	</div>

	<div id="the-story">
		<h3>Prolog</h3>
		<p>
			Po dokončení předchozího projektu v Zauzoo jsem dostal za úkol další
			důležitý projekt. Tentokrát jsem si zkusil práci na projektu pro
			Expobank, konkrétně na jejich novém internetovém bankovnictví.
			Nejpre jsem dostal na rozkoukání za úkol testovat jednu část
			aplikace, což pro mě bylo, jak je v Zazuoo zvykem, naprostou
			premiérou.
		</p>
		<div id="intro-flex" class="flex">
			<div class="flex-child-left">
				<h3>Problém</h3>
				<p class="left-text">
					Otestovat za pomocí frameworku KarmaJS aplikaci napsanou v
					Java frameworku Play. Ani s Playem, ani s Karmou jsem
					předtím neměl zkušenosti, takže jsem se všechno musel naučit
					za běhu.
				</p>
			</div>
			<div class="flex-child-right">
				<h3>Výsledek</h3>
				<p class="right-text">
					Díky velké pomoci kamaráda, který také pracoval v Zauzoo,
					jsem dokázal kvalitně otestovat část aplikace a u toho se
					naučil nové technologie a především Unit testování.
				</p>
			</div>
		</div>

		<Heading1
			description="Popis mého úkolu"
			heading="Testování internetového bankovnictví"
		/>
		<TextBlock
			text="Při nástupu do projektu již byla napsaná skoro celá codebase, takže jsem se opět ocitl ve španělské vesnici. Kromě toho mi bylo přiřazeno issue testování jedné části této aplikace, a já jsem neměl nejmenší tušení, jak takovou aplikaci testovat."
		/>
		<TextBlock
			text="Jediné, co mi bylo řečeno na začátku, bylo, jakou část mám otestovat a jaký framework se na to používá. Navíc byl celý projekt napsaný v Play Frameworku, na který se používá Java. To jsem taky používal poprvé a je to na dnešní standardy už poměrně zastaralý framework."
		/>
		<TextBlock
			text="Především díky pomoci dalšího kamaráda ze Zauzoo, který si prošel stejnou cestou jako já, jsem nakonec pochopil, co je vlastně mým úkolem a jak mám testy vlastně psát. Nakonec jsem napsal několik rozsáhlých testů a konečně pochopil, jak takové testování webové aplikace funguje."
		/>

		<h3 class="epilogue">Epilog</h3>
		<div class="flex " id="epilogue-div">
			<p>
				I přesto, že testování nepatří mezi nejzáživnější práce v IT,
				jsem za tuto zkušenost neskutečně vděčný. Poprvé jsem si zkusil,
				jak se testují weby a měl jsem tu možnost "zkoušet" si to rovnou
				na reálném projektu, což mě neustále motivovalo.
			</p>
		</div>
		<h3 class="epilogue">Ponaučení</h3>
		<div class="flex " id="epilogue-div">
			<div class="flex-child-left">
				<div class="lesson-title">
					Testování nuda je, má však cenné údaje
				</div>
				<p>
					Neustále jsem se musel nutit, abych testoval stále další a
					další aspekty, protože to ze začátku byla neskutečně náročná
					a nezvyklá aktivita, ale čím déle jsem to dělal a čím více
					funkcí jsem otestoval, tím rychleji mi to šlo a tím více mě
					to nakonec i bavilo.
				</p>
			</div>
			<div class="flex-child-right">
				<div class="lesson-title">Pomoc nad zlato</div>
				<p>
					Bez pomoci bych si vůbec nevěděl rady. Moc lidí už Play
					Framework nepoužívá, takže na internetu nebylo moc materiálů
					a KarmaJS taky dle mého nemá nejlepší dokumentaci. Takže bez
					rad kamaráda bych musel na vše přijít sám a má práce by mi
					trvala dvakrát tak dlouho.
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
