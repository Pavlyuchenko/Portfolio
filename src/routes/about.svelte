<section>
	<img
		loading="lazy"
		src="https://ik.imagekit.io/velkadomu/profile_edited_ACigk5OrM.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504386433"
		alt="Me, myself and I"
		id="profile"
	/>
	<div id="personal-info">
		<h3>About</h3>
		<hr />

		<h1>Hello, I'm <span style="color: var(--primary);">Michal</span></h1>
		<p id="main-desc">
			I'm a full-stack developer living in Opava, Czechia. I enjoy growing
			both as a person and as a developer, connecting with other
			like-minded people and solving interesting and challlenging
			problems.
		</p>
		<p id="desc">
			I'm currently a part-time front-end and test engineer at
			<a href="https://zauzoo.com" target="_blank">Zauzoo</a>. I created
			both the front-end and the back-end of projects
			<a href="https://velkadomu-sapper.vercel.app" target="_blank">
				VelkáDomů.cz
			</a>
			and
			<a href="https://slibotechny.cz" target="_blank">Slibotechny</a>.
			The main technologies I use to create an amazing web experience are
			Flask, Svelte and React.
		</p>
		<p id="desc">
			Until the end of May 2022, I will be attending Mendel's grammar
			school in Opava and after graduating, I hope I will study Data
			Science & Artificial Intelligence at Leiden University in
			Netherlands, because it seems to me like a logical and thrilling
			stepping stone into the diverse world of IT.
		</p>
		<p id="desc">
			When I'm not programming, designing or solving algorithmical
			puzzles, you may find me on a football field, watching sci-fi shows,
			reading (also mostly sci-fi) books, investing into stocks or crypto,
			or hanging out with my friends.
		</p>
		<p id="desc">
			I aspire to be an open-minded person with the ability to help my
			teammates, to learn new technologies and to be a well-read,
			physically fit and interesting person to talk to.
		</p>
		<p id="desc">
			Among my biggest programming achievments belongs landing the job at
			Zauzoo, reaching the 20th place in the whole Czechia in both
			<a
				href="https://mo.mff.cuni.cz/p/71/vysledky-3.pdf"
				target="_blank"
			>
				Math olympiad in programming
			</a>
			and a programming competition
			<a
				href="https://kasiopea.matfyz.cz/archiv/2021/finale/vysledky/"
				target="_blank"
			>
				Kasiopea
			</a>.
		</p>
	</div>
</section>
<div id="skills-wrapper">
	<h3>Skills</h3>
	<hr />
	<div class="skills">
		<div class="grid-column">
			<p>Python</p>
			<p>Flask</p>
			<p>SQL Alchemy</p>
			<p>React</p>
			<p>HTML & CSS</p>
		</div>
		<div class="grid-column">
			<p>Svelte</p>
			<p>Sapper</p>
			<p>KarmaJS</p>
			<p>Jasmine</p>
			<p>SEO</p>
		</div>
		<div class="grid-column">
			<p>Git, Github</p>
			<p>Material UI</p>
			<p>Figma</p>
			<p>Vercel</p>
		</div>
	</div>
</div>
<div id="skills-wrapper">
	<h3>Achievements</h3>
	<hr />
	<div class="skills">
		<div class="grid-column">
			<p>20th place, national round</p>
			<p style="font-weight: 400;">Maths olympiad in programming</p>
		</div>
		<div class="grid-column">
			<p>20th place, national round</p>
			<p style="font-weight: 400;">Programming competition Kasiopea</p>
		</div>
		<div class="grid-column">
			<p>1st place, national round</p>
			<p style="font-weight: 400;">High School Busines Challenge</p>
		</div>
	</div>
</div>

<style>
	section {
		margin-top: 50px;
		padding: 0px calc((100% - 73rem) / 2) 0px calc((100% - 73rem) / 2);

		display: flex;
		justify-content: space-between;
	}
	#profile {
		width: 40%;
	}
	#personal-info {
		width: 57%;
	}
	h3 {
		font-size: 16px;
		color: #666;
		margin-bottom: 12px;
	}
	h1 {
		margin-top: 30px;
		font-size: 40px;
		font-weight: 500;
	}
	#main-desc {
		font-size: 20px;
		line-height: 30px;
	}
	#desc {
		font-size: 18px;
		line-height: 25px;
	}
	#skills-wrapper {
		padding: 0px calc((100% - 73rem) / 2) 0px calc((100% - 73rem) / 2);
		margin-top: 80px;
	}
	.skills {
		grid-template-columns: repeat(3, 1fr);
		display: grid;
		grid-row-gap: 16px;
	}
	.skills p {
		margin-top: 7px;
		margin-bottom: 7px;
		font-weight: 500;
		font-size: 18px;
	}

	@media (max-width: 1250px) {
		section {
			display: block;
		}
		#profile {
			margin-left: 50%;
			transform: translateX(-50%);
			max-height: 400px;
			object-fit: cover;
		}
		#personal-info {
			width: 100%;
		}
	}
	@media (max-width: 500px) {
		#profile {
			width: 100%;
			max-height: 500px;
		}
	}
</style>
