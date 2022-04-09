<script>
	import ImageLoader from "../../components/ImageLoader.svelte";
	import ImageShowcase from "../../components/ImageShowcase.svelte";
	import Heading1 from "../../components/Heading1.svelte";
	import TextBlock from "../../components/TextBlock.svelte";
	import Bullet3 from "../../components/Bullet3.svelte";
</script>

<svelte:head>
	<title>VelkáDomů.cz | Michal Pavlíček</title>
</svelte:head>

<article>
	<div>
		<div>
			<p id="date">apr. 2019 - jul. 2019</p>
			<h1>Projekt Jídelna</h1>
			<p id="description">
				My first big project consisting of a backend and a CRUD
				database.
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
					<p class="project-info-title">My role</p>
					<p class="project-info-value" id="role">All</p>
				</div>
				<div>
					<p class="project-info-title">Technology</p>
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
					<p class="project-info-value" id="interval">4 months</p>
				</div>
			</div>
		</div>
	</div>

	<div id="the-story">
		<div id="alert">
			<span id="excl-mark">!</span>
			<span>
				This project is my first big project. More than creating an
				awesome app, the main goal of this project was learning. Take it
				with a grain of salt, please.
				<a href="/project/velka-domu">My best project.</a>
			</span>
		</div>
		<h3>Prologue</h3>
		<p>
			During presentation of interesting business ideas in geography
			lesson, one of my classmates came up with an interesting idea. The
			core of it was to take pictures of meals in our school canteen and
			then, when the same meal pops up let's say in a year, you will know
			what it looks like. It sounds silly, but the descriptions of meals
			and their actual look are far from being the same thing. A year
			after this proposal, I have taught myself programming and starting
			bringing this project to life with two other friends, who ended up
			doing nothing, since they were supposed to take photos of the
			pictures and assure marketing, and we never got to that point. Not
			that the website wasn't good, but we were too afraid of it.
		</p>
		<div id="intro-flex" class="flex">
			<div class="flex-child-left">
				<h3>Problem</h3>
				<p class="left-text">
					To create a webiste, where we could add photos of meals
					during the year and when we have enough records, to show
					them to all the students from my school. There should also
					be option to rate the meals, so that everyone knows what's
					best.
				</p>
			</div>
			<div class="flex-child-right">
				<h3>Result</h3>
				<p class="right-text">
					I created a simple website in Python's framework Flask
					allowing among other features logging in, adding photos and
					reviewing meals.
				</p>
			</div>
		</div>

		<Heading1
			description="A first real project"
			heading="Sometimes you gotta run before you can walk"
		/>
		<TextBlock
			text="This project was from the very beginning way above my programming skills. But since I follow the saying 'You learn by doing mistakes', I went all in to designing and programming the website My HTML and CSS possibilities were really bad, so was my Python skills, not even talking about Flask or design. "
		/>
		<TextBlock
			text="In the early beginning, I downloaded Figma for the first time in my life and I mocked up a basic design without knowing anything about it. Despite that, I got really into it and eventually created a good draft, which is however not good, really:"
		/>
		<ImageShowcase imgs={[
			{ path: "pj_landing.png", alt: "VFB" },
			{ path: "pj_landing_logged.png", alt: "VFB" },
			{ path: "pj_register.png", alt: "VFB" },
			{ path: "pj_recenze.png", alt: "VFB" },
			{ path: "pj_vyber.png", alt: "VFB" },
		]}
		/>

		<Heading1
			description="Functions of the website"
			heading="Earning experience is the priority"
		/>

		<TextBlock
			text="Due to many problems, the project never say the daylight, even though it was fully functional. The main routes were decent, the design was good enough and the backend could do magic, considering my skills back then. It could download data from the canteen servers even though it had no API and then even save the choices the user has made. Of course, you could rate the meals, comment, react with emojis... and a lot more."
		/>
		<TextBlock
			text="So the website was done and I would say some features were really good, such as reviewing the meals:"
		/>

		<ImageLoader
			path="pj_rating.gif"
			alt="VFB"
			description="Rating the meals"
		/>

		<TextBlock
			text="As a result, it's not a huge amazing project, I however wanted to show my journey and the process of learning. "
		/>

		<Heading1
			description="Lessons learned"
			heading="What mistakes I commited?"
		/>
		<Bullet3
			points={[
				{
					text: "No plan",
					image: "plan.png",
					content:
						"During programming, I usually changed up the plan due to the lack of plan.",
				},
				{
					text: "Inexperience with programming",
					image: "prog.png",
					content:
						"Even though I knew a bit of Python, I was not entirely sure in it.",
				},
				{
					text: "Not knowing the framework",
					image: "framework.png",
					content:
						"I used Flask for the first time in my life and this project was my tactic on how to learn it.",
				},
			]}
		/>

		<h3 class="epilogue">Epilogue</h3>
		<p>
			I label this project as my 'early days' project. It's nothing
			awesome, it's the other way round actually. It's really ugly. Thanks
			to it, I see the long way I've come and I know what I did in the
			early days. I'm so grateful I started it.
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
