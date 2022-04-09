<script>
	import Heading1 from "../../components/Heading1.svelte";
	import TextBlock from "../../components/TextBlock.svelte";
</script>

<article>
	<div>
		<div>
			<p id="date">jan. 2022 -</p>
			<h1>Testing Expobank</h1>
			<p id="description">
				I wrote tests for a big internet banking application using
				technologies Jasmine and KarmaJS.
			</p>
		</div>
		<div id="image">
			<img src="expobank_main.png" alt="Expobank logo" />

			<div id="project-info">
				<div>
					<p class="project-info-title">My role</p>
					<p class="project-info-value" id="role">Tester</p>
				</div>
				<div>
					<p class="project-info-title">Technologies</p>
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
					<p class="project-info-value" id="interval">3 months</p>
				</div>
			</div>
		</div>
	</div>

	<div id="the-story">
		<h3>Prolog</h3>
		<p>
			After finishing the previous project at Zauzoo, I received another
			interesting project as my task. This time, I tried working on a
			project for Expobank, specifically on their new internet banking. At
			first, I had to test one part of the application to get acquainted
			with the project. That task was completely new for me, as I had no
			prior experience with testing.
		</p>
		<div id="intro-flex" class="flex">
			<div class="flex-child-left">
				<h3>Problem</h3>
				<p class="left-text">
					Test a part of the webapp using the framework KarmaJS. The
					website was written using Java's framework Play. I had no
					experince using neither of these technologies, so I had to
					learn a lot.
				</p>
			</div>
			<div class="flex-child-right">
				<h3>Result</h3>
				<p class="right-text">
					Thanks to a huge help from a friend, who also used to work
					for Zauzoo, I managed to test a big part of the application
					and during that time, I learned a lot of new valuable thing
					such as Unit testing.
				</p>
			</div>
		</div>

		<Heading1
			description="Description of my task"
			heading="Testing the internet banking"
		/>
		<TextBlock
			text="During the beginning of my work on the project, most of the codebase was already written, so I felt kinda lost. Apart from that, I was given the task of testing and I had no idea of how to test such application."
		/>
		<TextBlock
			text="The only thing I was told in the beginning was what part of the app should I test and which framework I must use. On top of that, the project was written in Play Framework, for which you have to use Java. I used this framework for the first time in my life too."
		/>
		<TextBlock
			text="Especially thanks to the help of my friend at Zauzoo did I manage to finally understand what testing is all about and what actually should I do to accomplish the task I was given. In the end, I've written a number of tests and checked a lot of aspects of the application."
		/>

		<h3 class="epilogue">Epilogue</h3>
		<div class="flex " id="epilogue-div">
			<p>
				Despite the fact that testing doesn't belong to the most fun
				parts of IT, I am still very grateful for this experience. I
				tried for the first time in my life how websites are tested and
				I got the opportunity to test my abilities on real project,
				which kept me motivated.
			</p>
		</div>
		<h3 class="epilogue">Lessons learned</h3>
		<div class="flex " id="epilogue-div">
			<div class="flex-child-left">
				<div class="lesson-title">
					Testing is boring, but it is useful
				</div>
				<p>
					I had to force myself to keep on testing new and new things,
					since it felt unimaginably hard and unusual. But the longer
					I did that, the faster it got and the more entertaining it
					eventually was.
				</p>
			</div>
			<div class="flex-child-right">
				<div class="lesson-title">Help is better than gold</div>
				<p>
					Without help, I would be completely clueless. Not a lot of
					people use Play Framework anymore, so there isn't many
					materials on the internet. KarmaJS doesn't have a good
					documentation in my view as well, so I would have to learn
					all the thing by myself without help, which would have taken
					at least double the time it took.
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
