<script>
	import ImageLoader from "../../components/ImageLoader.svelte";
	import ImageShowcase from "../../components/ImageShowcase.svelte";
	import Heading1 from "../../components/Heading1.svelte";
	import Heading2 from "../../components/Heading2.svelte";
	import TextBlock from "../../components/TextBlock.svelte";
	import Bullet3 from "../../components/Bullet3.svelte";
</script>

<article>
	<div>
		<div>
			<p id="date">měsíc. rok - měsíc. rok</p>
			<h1>Název projektu</h1>
			<p id="description">
				Popis mého opravdu úžasného a užitečného projektu, který se bude
				v mém portfoliu vyjímat.
			</p>
		</div>
		<div id="image">
			<img loading="lazy" src="velka_domu_image.webp" alt="" />

			<div id="project-info">
				<div>
					<p class="project-info-title">Má role</p>
					<p class="project-info-value" id="role">Role</p>
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
					<p class="project-info-value" id="interval">x měsíců</p>
				</div>
			</div>
		</div>
	</div>

	<div id="the-story">
		<h3>Prolog</h3>
		<p>
			Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Excepteur
			sint occaecat cupidatat non proident, sunt in culpa qui officia
			deserunt mollit anim id est laborum. Mauris tincidunt sem sed arcu.
			Nulla quis diam. Duis sapien nunc, commodo et, interdum suscipit,
			sollicitudin et, dolor. Etiam posuere lacus quis dolor. In
			convallis. Aenean vel massa quis mauris vehicula lacinia.
		</p>
		<div id="intro-flex" class="flex">
			<div class="flex-child-left">
				<h3>Problém</h3>
				<p class="left-text">
					Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
					Excepteur sint occaecat cupidatat non proident, sunt in
					culpa qui officia deserunt mollit anim id est laborum.
					Mauris tincidunt sem sed arcu. Nulla quis diam.
				</p>
			</div>
			<div class="flex-child-right">
				<h3>Výsledek</h3>
				<p class="right-text">
					Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
					Excepteur sint occaecat cupidatat non proident, sunt in
					culpa qui officia deserunt mollit anim id est laborum.
					Mauris tincidunt sem sed arcu. Nulla quis diam. Lorem ipsum
					dolor sit amet, consectetuer adipiscing elit. Excepteur sint
					occaecat cupidatat non proident.
				</p>
			</div>
		</div>
		<hr />

		<!-- TO DO -->
		<ImageLoader path="vfb_image_test.png" alt="Test" />
		<ImageLoader path="vfb_screen.png" alt="Test" />
		<ImageLoader path="ffox.png" alt="Test" />
		<hr />
		<ImageShowcase
			imgs={[
				{ path: "vfb_screen.png", alt: "VFB" },
				{ path: "ffox.png", alt: "VFB" },
				{ path: "vfb_screen.png", alt: "VFB" },
			]}
		/>

		<Heading1 description="The Description" heading="Heading" />
		<TextBlock
			text="Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Mauris tincidunt sem sed arcu. Nulla quis diam. Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Mauris tincidunt sem sed arcu. Nulla quis diam."
		/>
		<Heading2 heading="Heading2" />
		<TextBlock
			text="Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Mauris tincidunt sem sed arcu. Nulla quis diam. Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Mauris tincidunt sem sed arcu. Nulla quis diam."
		/>
		<Heading1 description="The Description" heading="Heading" />
		<TextBlock
			text="Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Mauris tincidunt sem sed arcu. Nulla quis diam. Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Mauris tincidunt sem sed arcu. Nulla quis diam."
		/>

		<Bullet3
			points={[
				{
					text: "Search",
					image: "search.png",
					content:
						"Lorem upsum tolor sid amed. Lorem upsum tolor amed. Lorem upsum tolor sid amed. ",
				},
				{
					text: "Search",
					image: "search.png",
					content:
						"Lorem upsum tolor sid amed. Lorem upsum tolor amed. Lorem upsum tolor sid amed. ",
				},
				{
					text: "Search",
					image: "search.png",
					content:
						"Lorem upsum tolor sid amed. Lorem upsum tolor amed. Lorem upsum tolor sid amed. ",
				},
			]}
		/>

		<hr />

		<h3 class="epilogue">Epilog</h3>
		<div class="flex " id="epilogue-div">
			<div class="flex-child-left">
				<div class="lesson-title">Lorem ipsum</div>
				<p>
					Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
					Excepteur sint occaecat cupidatat non proident, sunt in
					culpa qui officia deserunt mollit anim id est laborum.
					Mauris tincidunt sem sed arcu. Nulla quis diam
				</p>
			</div>
			<div class="flex-child-right">
				<div class="lesson-title">Lorem ipsum</div>
				<p>
					Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
					Excepteur sint occaecat cupidatat non proident, sunt in
					culpa qui officia deserunt mollit anim id est laborum.
					Mauris tincidunt sem sed arcu. Nulla quis diam
				</p>
			</div>
		</div>
		<h3 class="epilogue">Ponaučení</h3>
		<div class="flex " id="epilogue-div">
			<div class="flex-child-left">
				<div class="lesson-title">Lorem ipsum</div>
				<p>
					Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
					Excepteur sint occaecat cupidatat non proident, sunt in
					culpa qui officia deserunt mollit anim id est laborum.
					Mauris tincidunt sem sed arcu. Nulla quis diam
				</p>
			</div>
			<div class="flex-child-right">
				<div class="lesson-title">Lorem ipsum</div>
				<p>
					Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
					Excepteur sint occaecat cupidatat non proident, sunt in
					culpa qui officia deserunt mollit anim id est laborum.
					Mauris tincidunt sem sed arcu. Nulla quis diam
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
