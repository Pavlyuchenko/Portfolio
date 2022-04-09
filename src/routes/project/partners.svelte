<script>
	import Heading1 from "../../components/Heading1.svelte";
	import TextBlock from "../../components/TextBlock.svelte";
</script>

<article>
	<div>
		<div>
			<p id="date">september. 2021 - december. 2021</p>
			<h1>Partners execution</h1>
			<p id="description">
				At my first job in company called Zauzoo I've worked on a
				project for a company offering financial advisory Partners and
				for the first time in my life had I been given the opportunity
				to cooperate with other programmers.
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
					<p class="project-info-title">My role</p>
					<p class="project-info-value" id="role">Front-end</p>
				</div>
				<div>
					<p class="project-info-title">Tech</p>
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
					<p class="project-info-value" id="interval">4 months</p>
				</div>
			</div>
		</div>
	</div>

	<div id="the-story">
		<h3>Prolog</h3>
		<p>
			I've gotten on board in a later phase of the project, which was
			quite a shock for me. Never before had I had to read code after
			other programmers nor did I have to change the code after them. The
			codebase was huge, but I managed to work through it pretty quickly.
			Not only that, I had to work in React, which was not my main JS
			framework at the time and I had to use the Material UI library,
			which was a premier for me.
		</p>
		<div id="intro-flex" class="flex">
			<div class="flex-child-left">
				<h3>Problem</h3>
				<p class="left-text">
					I was given the task of fixing the existing codebase and
					adding new functionality on the front-end according to the
					issues I was given on GitLab.
				</p>
			</div>
			<div class="flex-child-right">
				<h3>Result</h3>
				<p class="right-text">
					I managed to successfully work through dozens of issues that
					were later approved by other team members.
				</p>
			</div>
		</div>

		<Heading1
			description="The first working experience"
			heading="Work at Zauzoo"
		/>
		<TextBlock
			text="In September 2021 did I become for the first time in my life an employee at a software company. It was not a full-time job, but it was a big deal for me. In my first project, I was presented with the opportunity to work with another high-school student, with whom we became friends instantly and we are still helping each other even though we don't work together anymore. This was a huge bonus for me."
		/>
		<TextBlock
			text="During the work I did a lot of things for the first time in my life. I tried Git with multiple users for the first time, learnt a lot of new technologies (such as Material UI) and most importantly, working with other programmers."
		/>

		<hr />

		<h3 class="epilogue">Epilogue</h3>
		<p>
			I'm not entirely sure if I can show images from this project, so I
			rather chose not to. But nevertheless, I'm very thankful for the
			fact that I could've worked on this project, because it has
			broadened my horizons so much.
		</p>
		<h3 class="epilogue">Lessons learned</h3>
		<div class="flex " id="epilogue-div">
			<div class="flex-child-left">
				<div class="lesson-title">You don't know a lot</div>
				<p>
					In the beginning I thought I would be able to work through
					the issues easily. That of course didn't happen. Even the
					setup of the project on my machine was really tough,
					Material UI was hard and since the project was in a later
					phases, I was confused and didn't know what is where.
				</p>
			</div>
			<div class="flex-child-right">
				<div class="lesson-title">Don't be afraid to ask</div>
				<p>
					I was hesitant with asking for help, because I was scared I
					would be considered dumb, but it is much better to ask
					someone after trying too hard for the solution, since it is
					much faster and not as humiliating as it may seem.
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
