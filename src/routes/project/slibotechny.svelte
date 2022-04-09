<script>
	import ImageLoader from "../../components/ImageLoader.svelte";
	import Heading1 from "../../components/Heading1.svelte";
	import TextBlock from "../../components/TextBlock.svelte";
</script>

<article>
	<div>
		<div>
			<p id="date">august 2021</p>
			<h1>Slibotechny</h1>
			<p id="description">
				Watchdog of the promises of political parties in Czechia.
			</p>
		</div>
		<div id="image">
			<img
				src="slibotechny_preview.png"
				alt="Hlavní obrázek Slibotechny"
			/>

			<div id="project-info">
				<div>
					<p class="project-info-title">My role</p>
					<p class="project-info-value" id="role">Full-stack</p>
				</div>
				<div>
					<p class="project-info-title">Technologies</p>
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
					<p class="project-info-value" id="interval">1 month</p>
				</div>
			</div>
		</div>
	</div>

	<div id="the-story">
		<h3>Prologue</h3>
		<p>
			In the summer 2021 I found myself in a young and ambitious team full
			of people interested in politics. Together, we noticed the polarity
			in Czech society. Both these camps ususally claimed completely
			different information and noone knew, who was right. So we decided
			to change that. We track all the promises the parties made before
			elections and tell, what they really fulfill.
		</p>
		<div id="intro-flex" class="flex">
			<div class="flex-child-left">
				<h3>Problem</h3>
				<p class="left-text">
					To create two webapps: one for the admins who need to easily
					add and edit program points, and the second one for casual
					users, that has to be clean and usable.
				</p>
			</div>
			<div class="flex-child-right">
				<h3>Result</h3>
				<p class="right-text">
					The result was a quality website with the focus on precision
					and the best clarity possible. Responsibility is a necessity
					including clean design and easy controls.
				</p>
			</div>
		</div>

		<Heading1 description="Planning" heading="A clear idea" />
		<TextBlock
			text="When I joined the team, there was only an idea. They had however laid out an approximate layout of the page, so I only had to convert it to a digital form and they program everything from the bottom up. This was news for me, since so far, I was my own lord and I worked only for myself. Now I had to be accountablee to my coworkers, who were also my friends, and they definitely knew what they were talking about."
		/>
		<TextBlock
			text="After some time dedicated to designing a arrived to an almost final design, and I made it interesting by adding this dotted background. My coworkers liked the mockup, so I could soon start programming."
		/>
		<ImageLoader
			path="slibotechny_main_design.png"
			alt="Slibotechny hlavní design"
			description="First and final design of the party view."
		/>

		<Heading1
			description="Programming"
			heading="What is technically interesting??"
		/>
		<TextBlock
			text="Backend of this project isn't particularly interesting, it's only a CRUD with SQL database. There is a bunch of interesting things of the front-end. Firstly, I decided to go with a one page app, while there are no complete reloads from the server. This of course has its reason."
		/>
		<TextBlock
			text="When entering the page, no data are load from the back-end (well apart from the HTML and CSS) to decrease the loadtime as much as possible. The user then has to choose a party, which takes him to a category choice. There, once he hovers over some category with a mouse, that data downloads to the memory and when user clicks, the data is shown with almost no wait."
		/>
		<ImageLoader
			path="slibotechny_kategorie.png"
			alt="Výběr kategorie"
			description="Choice of a category of a promise. During hover, the data is downloaded."
		/>

		<hr />

		<h3 class="epilogue">Epilogue</h3>
		<p>
			As the result, the projects looks really great. As the desktop
			website, so the mobile version look amazing and they are user
			friendly. Thanks to the use of JS framework Sapper I ensured a great
			on-page SEO. The only problem users can face is the uncommon page
			without history, so the back button does not work.
		</p>
		<h3 class="epilogue">Lessons learned</h3>
		<div class="flex " id="epilogue-div">
			<div class="flex-child-left">
				<div class="lesson-title">Think through your decisions</div>
				<p>
					When I decided to go with this structure of the website, I
					didn't think through the pros and cons completely. Don't get
					me wrong, it turned out great, but it didn't have to. The UX
					might be suffering from time to time, but in my opinion,
					it's worth it.
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
