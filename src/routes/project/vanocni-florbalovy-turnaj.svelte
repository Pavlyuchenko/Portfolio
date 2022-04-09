<script>
	import ImageLoader from "../../components/ImageLoader.svelte";
	import ImageShowcase from "../../components/ImageShowcase.svelte";
	import Heading1 from "../../components/Heading1.svelte";
	import TextBlock from "../../components/TextBlock.svelte";
</script>

<article>
	<div>
		<div>
			<p id="date">apr. 2020 - jun. 2020</p>
			<h1>Unihockey school tournament</h1>
			<p id="description">
				Web application for annual sports event at my high school with
				real-time results support.
			</p>
		</div>
		<div id="image">
			<img
				src="vfb_main.png"
				alt="Vánoční florbalový turnaj hlavní obrázek"
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
							loading="lazy"
							src="react.png"
							alt="React logo"
							title="React"
						/>
						<img
							src="python.png"
							alt="Python logo"
							title="Python"
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
					<p class="project-info-value" id="interval">3 months</p>
				</div>
			</div>
		</div>
	</div>

	<div id="the-story">
		<h3>Prologue</h3>
		<p>
			At Mendel's grammar school in Opava, there is an annual Unihockey
			tournament. There, all the people from the school play against each
			other, including the teachers. The aim of this project is to make
			this event modern with a web app showing the current standings and
			live results.
		</p>
		<div id="intro-flex" class="flex">
			<div class="flex-child-left">
				<h3>Problem</h3>
				<p class="left-text">
					To create a simple, clear and responsive site showing the
					current state of the tournament.
				</p>
			</div>
			<div class="flex-child-right">
				<h3>Result</h3>
				<p class="right-text">
					I created an effective real-time application showing the
					current results for a school tournament with support of two
					concurrent matches.
				</p>
			</div>
		</div>

		<Heading1
			description="To grab the user's attention"
			heading="The landing page"
		/>
		<TextBlock
			text="The first impression is almost everything. The landing page is therefore the most important thing on this whole project. That's why I decided to put a decision in front of the user right from the beginning, which looks elegant and professional however."
		/>
		<TextBlock
			text="The user chooses his favorit team in the beginning. This decision shows itself it the way of notification about when this team plays and other similar information like their current standings."
		/>
		<ImageLoader
			path="VFB_team_choice.gif"
			alt="Výběr týmu"
			description="The reactive team choice."
		/>

		<Heading1
			description="The UI"
			heading="Presenting information to the user"
		/>
		<TextBlock
			text="After the initial choice, the user finds themselves on the main dashboard. There is a navigation, details about the currently playing matches, the next matches and the standing of the playing group. Shortly everything a user might want to know."
		/>
		<TextBlock
			text="Everything tries to feel as easily and clearly as possible, while being graphically pleasant."
		/>
		<ImageLoader
			path="vfb_landing.png"
			alt="Dashboard"
			description="Primary dashboard with the most imporatant infromation."
		/>

		<Heading1
			description="Admin dashboard"
			heading="How do information get to the system?"
		/>
		<ImageLoader
			path="vfb_showcase.gif"
			alt="Ukázka real-time updatování informací"
			description="Updating information from the back-end."
		/>
		<TextBlock
			text="The basis of such websites must be entering the data into the database. I decided to connect this feature with timekeeping and standings, since it is important to show the teams the current scord. So during the match, there is the score on the monitor, which gets send to the BE upon change and when done, all the information get written to the database."
		/>
		<TextBlock
			text="The cherry on tom is the fact that the information flows to the users in real-time, so they have an overview about the current matches even if they are not in the gym at the moment."
		/>
		<ImageLoader
			path="VFB_real_time.gif"
			alt="Real time ukázka"
			description="Showing information in real time."
		/>

		<Heading1
			description="Additional functionality"
			heading="Responsivity and other stuff"
		/>
		<TextBlock
			text="The site of course offers other expanding features such as team detail or even match detail, where you can see when goals were scored. It's of course a neccessity a schedule of following matches or a group table."
		/>
		<TextBlock
			text="Apart from that I had also assured the responsivity of the webisite, since its main use is intended to be on mobile phones. The event takes place in a gym, so the users won't have a desktop, obviously."
		/>
		<ImageShowcase
			imgs={[
				{ path: "vfb_detail.png", alt: "Detail týmu" },
				{ path: "vfb_rozpis.png", alt: "Rozpis zápasů" },
				{ path: "vfb_mobile.png", alt: "Mobilní verze" },
			]}
		/>

		<hr />

		<h3 class="epilogue">Epilogue</h3>
		<div>
			<p>
				In the end I must say it is a really great website. Everything
				feels modern and smoothly with a nice design. It offers its
				users all the needed informations clearly a allows the teams to
				look up their upcoming matches and other information.
			</p>
		</div>
		<h3 class="epilogue">Lessons learned</h3>
		<div class="flex " id="epilogue-div">
			<div class="flex-child-left">
				<div class="lesson-title">Expect the impossible</div>
				<p>
					I programmed the website enough in advance in summer 2020 in
					order to deliver it to Christmas the same year. But Covid
					came and all my work seemed useless, even though it got used
					the year after.
				</p>
			</div>
			<div class="flex-child-right">
				<div class="lesson-title">Mobile first</div>
				<p>
					I spent a lot of time tweaking the desktop version, even
					though nobody used it, really. I should've focused on the
					mobiles only and don't care about the desktop so much.
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
