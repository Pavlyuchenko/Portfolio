<script>
	import ImageLoader from "../../components/ImageLoader.svelte";
	import ImageShowcase from "../../components/ImageShowcase.svelte";
	import Heading1 from "../../components/Heading1.svelte";
	import TextBlock from "../../components/TextBlock.svelte";
	import Bullet3 from "../../components/Bullet3.svelte";
</script>

<svelte:head>
	<title>SIR Model | Michal Pavlíček</title>
</svelte:head>

<article>
	<div>
		<div>
			<p id="date">mar. 2020 - apr. 2020</p>
			<h1>SIR Model</h1>
			<p id="description">
				Javascript animation simulating the simplest model of a course
				of epidemics.
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
					<p class="project-info-title">My role</p>
					<p class="project-info-value" id="role">All</p>
				</div>
				<div>
					<p class="project-info-title">Technology</p>
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
					<p class="project-info-value" id="interval">1 month</p>
				</div>
			</div>
		</div>
	</div>

	<div id="the-story">
		<h3>Prologue</h3>
		<p>
			<a
				href="https://pavlyuchenko.github.io/SIRModel/"
				target="_blank"
			>
				Demo of the project.
			</a>
			<br />
			In March 2020, the world epidemics of Covid-19 started a I, as well as
			all my friends found myself home without school suddenly, almost without
			any academic requests. At first, I experienced excitement, since the
			first holidays of this kind in history was taking place and the situation
			in Czechia was kinda calm. Then, one of the most well-known educatinal
			Youtuber
			<a href="https://www.youtube.com/c/3blue1brown" target="_blank">
				3Blue1Brown
			</a>
			created
			<a href="https://youtu.be/gxAaO2rsdIs" target="_blank">a video</a>,
			in which he described the simplest epidemiological model. That
			inspired me to code up the same this, but make it random so that the
			user sees a new simulation every time. I did so to fill the gaps in
			my undestanding of Vanilla Javascript and to learn &lt;canvas&gt;.
		</p>
		<div id="intro-flex" class="flex">
			<div class="flex-child-left">
				<h3>Problem</h3>
				<p class="left-text">
					Create a rather simple simulation of Covid epidemics and
					overcome procrastination, since I had unlimited time on my
					hands.
				</p>
			</div>
			<div class="flex-child-right">
				<h3>Result</h3>
				<p class="right-text">
					I learned how to use &lt;canvas&gt; and created an
					application simulating the real course of action kinda
					realistically.
				</p>
			</div>
		</div>

		<Heading1
			description="Simulation of pandemics"
			heading="Using SIR model"
		/>
		<TextBlock
			text="The project uses the simplest SIR model to simulate the course of epidemics. Its principle is kinda simple and clear:"
		/>
		<TextBlock
			text="In a simulation in an imaginary city, there is a lot of people, who don't go past its borders. These people can be in three different states:"
		/>

		<Bullet3
			points={[
				{
					text: "Healthy",
					image: "blue.png",
					content: "",
				},
				{
					text: "Infected",
					image: "red.png",
					content: "",
				},
				{
					text: "Healed/Dead",
					image: "grey.png",
					content: "",
				},
			]}
		/>
		<TextBlock
			text="Every infected individual has an invisible circle around himself. When a healthy person goes inside it there is a slight chance he will get infected too. After some time, infected people become 'grey'."
		/>

		<ImageLoader
			path="https://ik.imagekit.io/velkadomu/sir_VBf0dO0NC.gif?ik-sdk-version=javascript-1.4.3&updatedAt=1649504401287"
			alt="VFB"
			description="A short showcase of the simulation"
		/>

		<TextBlock
			text="Canvas works on a principle of continuous rewriting of the whole area. In each frame, the whole 'scenery' gets deleted and new 'inhabitants' are created. During that, their distance is also calculated and decided, if some people should get infected."
		/>

		<Heading1
			description="Lessons learned"
			heading="What mistakes I commited?"
		/>
		<Bullet3
			points={[
				{
					text: "Not enough of refactorization",
					image: "refactor.png",
					content:
						"The codebase of this project is not as solid as it should be.",
				},
				{
					text: "Learning on the go",
					image: "book.png",
					content:
						"To earn experience is this attitude one of the best, not so much for having best results.",
				},
				{
					text: "Complexity was too big",
					image: "settings.png",
					content:
						"A few hundred of moving circles is not the easiest thing for the processor, so I should've come up with a better algorithm.",
				},
			]}
		/>

		<h3 class="epilogue">Epilogue</h3>
		<p>
			Thanks to this project I understood how the HTML canvas works and
			overall, how animation on websites work. I have used this valuable
			experience in later projects, where they were used usefully, not
			just for mere learning experience.
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
