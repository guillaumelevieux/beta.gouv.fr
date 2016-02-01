---
title: Réalisations
additional_css: homepage
---
<section id="mission-statement">
	<img src="img/header.jpg" alt="" />
	<h1>{{ site.description }}</h1>
</section>

<section id="about">
	<h2><a href="{{ 'a-propos' | prepend:site.baseurl }}">Nos principes</a></h2>
</section>

<section id="dashboard">
	<h2>Nous avons actuellement…</h2>

	<ol class="counter--incubation">
		{% for phase in site.phases.incubation %}
			<li class="counter {{ phase[0] }}">
				<span class="counter--count">{{ site.startups | where:'status',phase[0] | size }}</span>
				<i>produits en</i>
				<span title="{{ phase[1].description }}" class="tooltip counter--name">{{ phase[1].name }}</span>
			</li>
		{% endfor %}

		<li>
			<ul class="counter--endgame">
				{% for phase in site.phases.endgame %}
					<li class="counter {{ phase[0] }}">
						<span class="counter--count">{{ site.startups | where:'status',phase[0] | size }}</span>
						<i>produits en</i>
						<span title="{{ phase[1].description }}" class="tooltip counter--name">{{ phase[1].name }}</span>
					</li>
				{% endfor %}
			</ul>
		</li>
	</ol>
</section>

<section id="startups">
	{% for startup in site.startups %}
		{% include startup.html description=startup %}
	{% endfor %}
</section>