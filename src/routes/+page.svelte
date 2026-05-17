<script>
	const projects = [
		{
			title: 'StockPulse',
			description:
				'A PWA for tracking a Swedish Avanza stock portfolio with EMA-based BUY/SELL/HOLD signals. Deployed on Cloudflare Pages with a proxy Worker for Yahoo Finance data.',
			tech: ['SvelteKit', 'Cloudflare Workers', 'PWA', 'Yahoo Finance API'],
			url: '#'
		},
		{
			title: 'Project Two',
			description:
				'A brief description of what this project does and the problem it solves. Replace with your own project details.',
			tech: ['React', 'Node.js', 'PostgreSQL'],
			url: '#'
		},
		{
			title: 'Project Three',
			description:
				'A brief description of what this project does and the problem it solves. Replace with your own project details.',
			tech: ['Vue', 'Python', 'AWS'],
			url: '#'
		}
	];
</script>

<svelte:head>
	<title>Robert Olsson — Full Stack Developer</title>
</svelte:head>

<div class="site">
	<header class="header">
		<nav class="nav container">
			<span class="logo">Robert Olsson</span>
			<ul class="nav-links">
				<li><a href="#about">About</a></li>
				<li><a href="#projects">Projects</a></li>
				<li><a href="#contact">Contact</a></li>
			</ul>
		</nav>
	</header>

	<main>
		<section class="hero">
			<div class="container">
				<p class="hero-eyebrow">Full Stack Developer</p>
				<h1 class="hero-heading">Building software that's fast, usable, and built to last.</h1>
				<p class="hero-sub">
					I help companies ship high-quality products — from architecture and APIs to polished,
					accessible UIs.
				</p>
				<a href="#contact" class="btn">Get in touch →</a>
			</div>
		</section>

		<section id="about" class="section">
			<div class="container about-grid">
				<div class="about-text">
					<h2 class="section-heading">About</h2>
					<p>
						I'm a full-stack developer with a sharp focus on three things: usability, speed, and
						quality. I care deeply about the end user experience — every interaction, every load time,
						every edge case.
					</p>
					<p>
						I work across the stack, from database design and API architecture to accessible, polished
						frontends. Whether it's a greenfield build or untangling legacy code, I bring the same
						discipline and attention to detail.
					</p>
				</div>
				<div class="focus-areas">
					<div class="focus-card">
						<span class="focus-icon">⚡</span>
						<h3>Performance</h3>
						<p>Fast by default. I optimise for real-world metrics — Core Web Vitals, TTFB, and perceived speed.</p>
					</div>
					<div class="focus-card">
						<span class="focus-icon">✦</span>
						<h3>Usability</h3>
						<p>Software should be intuitive. I think deeply about user flows and eliminate friction at every step.</p>
					</div>
					<div class="focus-card">
						<span class="focus-icon">◆</span>
						<h3>Quality</h3>
						<p>Clean architecture, maintainable code, and thoughtful testing — built to last beyond the launch.</p>
					</div>
				</div>
			</div>
		</section>

		<section id="projects" class="section section--alt">
			<div class="container">
				<h2 class="section-heading">Selected Projects</h2>
				<div class="projects-grid">
					{#each projects as project}
						<article class="project-card">
							<h3 class="project-title">{project.title}</h3>
							<p class="project-desc">{project.description}</p>
							<ul class="tech-tags">
								{#each project.tech as tag}
									<li class="tech-tag">{tag}</li>
								{/each}
							</ul>
						</article>
					{/each}
				</div>
			</div>
		</section>

		<section id="contact" class="section">
			<div class="container contact">
				<h2 class="section-heading">Let's work together</h2>
				<p class="contact-sub">
					I'm available for consulting engagements. If you have a project in mind, I'd love to hear
					about it.
				</p>
				<a href="mailto:robert.olsson@pure.se" class="btn">robert.olsson@pure.se →</a>
			</div>
		</section>
	</main>

	<footer class="footer">
		<div class="container">
			<p>© 2026 Robert Olsson</p>
		</div>
	</footer>
</div>

<style>
	:global(*),
	:global(*::before),
	:global(*::after) {
		box-sizing: border-box;
		margin: 0;
		padding: 0;
	}

	:global(html) {
		scroll-behavior: smooth;
	}

	:global(body) {
		font-family: 'Inter', system-ui, -apple-system, sans-serif;
		color: #0f172a;
		background: #ffffff;
		line-height: 1.6;
		-webkit-font-smoothing: antialiased;
	}

	:global(a) {
		color: inherit;
		text-decoration: none;
	}

	.container {
		max-width: 1100px;
		margin: 0 auto;
		padding: 0 1.5rem;
	}

	/* Header */
	.header {
		position: sticky;
		top: 0;
		background: rgba(255, 255, 255, 0.92);
		backdrop-filter: blur(8px);
		border-bottom: 1px solid #f1f5f9;
		z-index: 100;
	}

	.nav {
		display: flex;
		align-items: center;
		justify-content: space-between;
		height: 4rem;
	}

	.logo {
		font-weight: 600;
		font-size: 1rem;
		letter-spacing: -0.01em;
	}

	.nav-links {
		display: flex;
		gap: 2rem;
		list-style: none;
	}

	.nav-links a {
		font-size: 0.9rem;
		color: #475569;
		transition: color 0.2s;
	}

	.nav-links a:hover {
		color: #0f172a;
	}

	/* Hero */
	.hero {
		padding: 7rem 0 6rem;
		border-bottom: 1px solid #f1f5f9;
	}

	.hero-eyebrow {
		font-size: 0.8rem;
		font-weight: 600;
		color: #2563eb;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		margin-bottom: 1.25rem;
	}

	.hero-heading {
		font-size: clamp(2.2rem, 5vw, 3.5rem);
		font-weight: 700;
		line-height: 1.15;
		letter-spacing: -0.03em;
		max-width: 700px;
		margin-bottom: 1.5rem;
	}

	.hero-sub {
		font-size: 1.1rem;
		color: #475569;
		max-width: 520px;
		margin-bottom: 2.5rem;
		line-height: 1.7;
	}

	/* Button */
	.btn {
		display: inline-block;
		background: #0f172a;
		color: #ffffff;
		padding: 0.75rem 1.5rem;
		border-radius: 6px;
		font-size: 0.9rem;
		font-weight: 500;
		transition:
			background 0.2s,
			transform 0.15s;
	}

	.btn:hover {
		background: #1e293b;
		transform: translateY(-1px);
	}

	/* Sections */
	.section {
		padding: 5rem 0;
	}

	.section--alt {
		background: #f8fafc;
	}

	.section-heading {
		font-size: 1.75rem;
		font-weight: 700;
		letter-spacing: -0.02em;
		margin-bottom: 2rem;
	}

	/* About */
	.about-grid {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 4rem;
		align-items: start;
	}

	.about-text p {
		color: #475569;
		margin-bottom: 1rem;
		line-height: 1.75;
	}

	.focus-areas {
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}

	.focus-card {
		padding: 1.25rem 1.5rem;
		border: 1px solid #e2e8f0;
		border-radius: 10px;
		background: #ffffff;
	}

	.focus-icon {
		font-size: 1rem;
		margin-bottom: 0.5rem;
		display: block;
		color: #2563eb;
	}

	.focus-card h3 {
		font-size: 0.95rem;
		font-weight: 600;
		margin-bottom: 0.35rem;
	}

	.focus-card p {
		font-size: 0.875rem;
		color: #64748b;
		line-height: 1.6;
	}

	/* Projects */
	.projects-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
		gap: 1.5rem;
	}

	.project-card {
		background: #ffffff;
		border: 1px solid #e2e8f0;
		border-radius: 10px;
		padding: 1.75rem;
		transition:
			border-color 0.2s,
			box-shadow 0.2s;
	}

	.project-card:hover {
		border-color: #94a3b8;
		box-shadow: 0 4px 24px rgba(0, 0, 0, 0.06);
	}

	.project-title {
		font-size: 1.05rem;
		font-weight: 600;
		margin-bottom: 0.75rem;
		letter-spacing: -0.01em;
	}

	.project-desc {
		font-size: 0.875rem;
		color: #475569;
		margin-bottom: 1.25rem;
		line-height: 1.7;
	}

	.tech-tags {
		display: flex;
		flex-wrap: wrap;
		gap: 0.4rem;
		list-style: none;
	}

	.tech-tag {
		font-size: 0.72rem;
		font-weight: 500;
		background: #f1f5f9;
		color: #475569;
		padding: 0.25rem 0.625rem;
		border-radius: 99px;
	}

	/* Contact */
	.contact {
		text-align: center;
		max-width: 520px;
		margin: 0 auto;
	}

	.contact-sub {
		color: #475569;
		margin-bottom: 2rem;
		line-height: 1.75;
	}

	/* Footer */
	.footer {
		padding: 2rem 0;
		border-top: 1px solid #f1f5f9;
		text-align: center;
		font-size: 0.8rem;
		color: #94a3b8;
	}

	/* Responsive */
	@media (max-width: 768px) {
		.about-grid {
			grid-template-columns: 1fr;
			gap: 2.5rem;
		}

		.nav-links {
			gap: 1.25rem;
		}

		.hero {
			padding: 4.5rem 0 4rem;
		}
	}
</style>
