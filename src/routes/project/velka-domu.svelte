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
			<p id="date">nov. 2020 - feb. 2021</p>
			<h1>VelkáDomů.cz</h1>
			<p id="description">
				CMS system, front-end page and a CRUD database for an ambitious
				football portal.
			</p>
		</div>
		<div id="image">
			<img
				src="https://ik.imagekit.io/velkadomu/velkadomu2_iJO5yyCvzT.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504383080"
				alt="VelkáDomů hlavní obrázek"
				id="main-image"
			/>

			<div id="project-info">
				<div>
					<p class="project-info-title">My role</p>
					<p class="project-info-value" id="role">All</p>
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
					<p class="project-info-value" id="interval">3 months</p>
				</div>
			</div>
		</div>
	</div>

	<div id="the-story">
		<h3>Prologue</h3>
		<p>
			<b><a href="https://velkadomu-sapper.vercel.app/" target="_blank">Link to the project</a></b><br>
			At the start of November 2020 I joined with my classmate to create
			our own website, where we could present our own football news. My
			concern was the technical side of things, his job was marketing and
			getting authors. The main aim of this project was getting a large
			audience for who we would be the main source of football news, to
			earn valuable experience from the area of business and to try
			working in a team.
		</p>
		<div id="intro-flex" class="flex">
			<div class="flex-child-left">
				<h3>Problem</h3>
				<p class="left-text">
					My job was to create a web app from top to bottom including
					design, back-end and front-end. I programmed two versions,
					one for a usual reader, the second for writers, which
					includes creating an ediotrial system and
					<a
						href="/showcase/text-editor"
						style="text-decoration: underline; cursor: pointer;"
						target="_blank"
					>
						a text processor
					</a>. Responsivness was a necessity.
				</p>
			</div>
			<div class="flex-child-right">
				<h3>Result</h3>
				<p class="right-text">
					In the span of four months I delivered a fully functional
					responsive webapp optimalized for SEO including an interface
					for editors and an advanced text editor.
				</p>
			</div>
		</div>

		<Heading1 description="The look" heading="No design, no deal" />
		<TextBlock
			text="The first step was creating the design and agreed on the functions of the project. Creating the design first is neccessary since we could discuss the features together and tamper with the details quickly. After a few days we came to a design that looked like this:"
		/>

		<ImageLoader
			path="https://ik.imagekit.io/velkadomu/first_design_I-Kx68cVy.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504360274"
			alt="VFB"
			description="The first design of VelkáDomů.cz"
		/>

		<TextBlock
			text="This version on one hand looks friendly, but the reader is immediately presented with a lot of colors and informations and they become overwhelmed. Apart from the three main articles, this version lacks visual hierarchy a confuses the reader. That's why decided to create an another version, which improves visual hierarchy and brings consistent look:"
		/>
		<ImageLoader
			path="https://ik.imagekit.io/velkadomu/new_design_015Q2S8xp.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504369462"
			alt="VFB"
			description="Final design"
		/>

		<TextBlock
			text="The new version doesn't overwhelm the reader, since it only shows four articels upon arival. It only presents other, less important, informations lower including other actual articles. After we consulted it with other poeple, we decided to choose the latter vesion due to this arguments:"
		/>
		<Bullet3
			points={[
				{
					text: "Visual hierarchy",
					image: "crown.png",
					content:
						"The site has clearly stated the most distinctive elements, thanks to which the user knows where to look.",
				},
				{
					text: "Uniqueness",
					image: "unique.png",
					content:
						"The design is memorable and easily sticks in the user's memory.",
				},
				{
					text: "Simplicity",
					image: "simple.png",
					content:
						"Despite the former points, the design is still clear and without screamy elements.",
				},
			]}
		/>

		<Heading1
			description="Used technologies"
			heading="Tech stack of our project"
		/>
		<TextBlock
			text="After the visual side of things was done, the programming part kicked in. For this project, we chose these technologies:"
		/>
		<Bullet3
			points={[
				{
					text: "Backend - Flask",
					image: "flask.png",
					content:
						"I chose Framework Flask because I know it really well and it's very easy to work with.",
				},
				{
					text: "Frontend - Sapper",
					image: "sapper.png",
					content:
						"Sapper is a server-rendered framework from Svelte, which ensures a good SEO as well as the development speed.",
				},
				{
					text: "Database - SQLAlchemy",
					image: "sqlalchemy.png",
					content:
						"SQLAlchemy is greatly customized to work with Flask, so it's a sure choice despite its lack of some features.",
				},
			]}
		/>

		<Heading1
			description="Environment for the editors"
			heading="What the user doesn't see, that doesn't hurt them"
			id="texteditor"
		/>

		<ImageLoader
			path="https://ik.imagekit.io/velkadomu/text_editor_KOK-YZm91.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504375687"
			alt="Text editor"
			description="Text editor programmed for the editorial system."
		/>

		<TextBlock
			text="At first, the programming of the editorial system came up. This process split to two main problems: the text editor a articles managment. When I created the text-editor, I could've gone for the classic out-of-the-box WYSIWYG solution. But one of the targets of this projects was learning, so I decided to code up my own block-based text editor. Its basic demo can be found <a href='/showcase/text-editor' target='_blank'>here</a>."
		/>

		<ImageLoader
			path="https://ik.imagekit.io/velkadomu/resizedTextEditor_Y8hJGfwVc.gif?ik-sdk-version=javascript-1.4.3&updatedAt=1649504402704"
			alt="Text editor"
			description="Text editor programmed for the editorial system"
		/>

		<TextBlock
			text="The editor in its final form automatically saves the work of editors and after they are finished, the result is transformed into HTML in back-end. Once the editor was done, it was trivial to make the other things visually appealing create a table with all the articles and to program other features."
		/>
		<TextBlock
			text="<i style='font-size: 17px;'>(In short do these features represent: the editorial system has two roles for editors: a regular admin and a 'superadminem' for main team members. Admin can only write articles and 'quickies' and look at their own stats, while superadmin sees stats of everyone else a can set, which articles are set as main on the landing page.)</i>"
		/>
		<TextBlock
			text="Since this interface is not vital for SEO and the regular user won't see them, the design is not the most important thing. More vital are these aspects:"
		/>
		<Bullet3
			points={[
				{
					text: "Simplicity",
					image: "simple.png",
					content:
						"The editor must clearly know, where are what features, so that they can focus on writing.",
				},
				{
					text: "Clarity",
					image: "clarity.png",
					content:
						"The content of the pages can't be overcrowded, in order not to overwhelm the editor.",
				},
				{
					text: "Flawlessness",
					image: "flawless.png",
					content:
						"Editors are not programmers. If something goes wrong, they won't know what to do. So the system must be presice.",
				},
			]}
		/>
		<ImageShowcase
			imgs={[
				{ path: "https://ik.imagekit.io/velkadomu/admin_JfcTeqr3t0.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504356055", alt: "VFB" },
				{
					path: "https://ik.imagekit.io/velkadomu/title_image_AegigQ3wo.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504382372",
					alt: "VFB",
				},
				{ path: "https://ik.imagekit.io/velkadomu/cms_qCXYiLKQ4.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504358201", alt: "VFB" },
				{
					path: "https://ik.imagekit.io/velkadomu/rychlovky_4Stm5cOc3.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504371494",
					alt: "VFB",
				},
				{ path: "https://ik.imagekit.io/velkadomu/nova_rychlovka_sFJigWhyt.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504360824", alt: "VFB" },
			]}
		/>

		<Heading1
			description="The user interface"
			heading="Our reader, our lord"
		/>
		<TextBlock
			text="Contrary to the editorial system, design matters the most concerning the regular user. At this point, I had to join everything together, so the result looks like this:"
		/>

		<ImageLoader
			path="https://ik.imagekit.io/velkadomu/scheme_CfxTXOjqY.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504367422"
			alt="Scheme"
			description="How does VelkáDomů.cz work?"
		/>

		<TextBlock
			text="During programming the UI for readers, there was constant testing with my friends across many platforms. In this final step, it was all about getting the data from the server and displaying them on the page nicely using HTML and CSS. This step also included creating my own login system, user surveys and responsivity. The result can be seen here <a href='https://velkadomu-sapper.vercel.app/' target='_blank'>velkadomu.cz</a> (example account: test@test.test, heslo: Testing123) or on the following images:"
		/>
		<ImageShowcase
			imgs={[
				{ path: "https://ik.imagekit.io/velkadomu/landing_velka_domu_mc0GHG2k4.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504367959", alt: "VFB" },
				{
					path: "https://ik.imagekit.io/velkadomu/nejnovejsi_clanky_velka_domu_BVGRa_lhFh.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504374779",
					alt: "VFB",
				},
				{ path: "https://ik.imagekit.io/velkadomu/clanek_velka_domu__jKb8QIOa.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504358101", alt: "VFB" },
				{
					path: "anketa1.gif",
					alt: "VFB",
					altPath: "anketa.png",
				},
				{ path: "https://ik.imagekit.io/velkadomu/kalendar_Y40qlvWRi.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504359340", alt: "VFB" },
				{
					path: "https://ik.imagekit.io/velkadomu/mobile_velka_domu_Yvl8AVJSE.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504372608",
					alt: "VFB",
				},
			]}
		/>
		<ImageLoader
			path="https://ik.imagekit.io/velkadomu/landing_mobile_4lnVUnayw.gif?ik-sdk-version=javascript-1.4.3&updatedAt=1649504396436"
			alt="Landing mobile"
			description="The main mobile site VelkáDomů.cz"
			width="30"
		/>

		<h3 class="epilogue">Epilogue</h3>
		<p>
			To be the only full-stack developer of such big project is not as
			easy as it seems. For the first time in my life have I tried working
			in a team, where a lot of other people depend on me and I can't
			possibly fail. Even though I was the only person involved in the
			technical side of thing, I managed to create it all without bigger
			problems and I received experience from all corners of development.
		</p>
		<h3 class="epilogue">Lessons learned</h3>
		<div class="flex " id="epilogue-div">
			<div class="flex-child-left">
				<div class="lesson-title">Communicate twice, develop once</div>
				<p>
					During the course of the project, we consulted everything
					mainly among four eyes and even in the smallest possible
					team, we sometimes couldn't agree on some things. That was
					new for me, because before, I could do everything on my own.
				</p>
			</div>
			<div class="flex-child-right">
				<div class="lesson-title">Don't assume, be sure</div>
				<p>
					I created project of such size for the first time, that's
					why many functions were experimenting and examining, how the
					things work. I assumed, that once everything will be done, I
					will only add support for sharing articles on social media.
					Then I found out, that you can't really do that with Svelte
					and that you have to use server-side rendering. So it took a
					while to rewrite everything.
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

	#main-image {
		border-radius: 5px 5px 0 0;
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
