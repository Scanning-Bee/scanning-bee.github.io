<script lang="ts">
	import { _ } from "svelte-i18n";

	import {
		defaultI18nValues,
		entries,
		FeatureCard,
		HeaderChip,
		PageSection,
	} from "$lib";

	import { base } from "$app/paths";
	import type { Technology } from "$data/technologies";

	const technologies: Technology[] = [
		{
			name: "React",
			src: base + "/ui/technologies/react.png",
			link: "https://reactjs.org/",
		},
		{
			name: "TypeScript",
			src: base + "/ui/technologies/ts.png",
			link: "https://www.typescriptlang.org/",
		},
		{
			name: "Electron",
			src: base + "/ui/technologies/electron.png",
			link: "https://www.electronjs.org/",
		},
		{
			name: "Django",
			src: base + "/ui/technologies/django.png",
			link: "https://www.djangoproject.com/",
		},
		{
			name: "Docker",
			src: base + "/ui/technologies/docker.png",
			link: "https://www.docker.com/",
		},
		{
			name: "Python",
			src: base + "/ui/technologies/python.png",
			link: "https://www.python.org/",
		},
		{
			name: "OpenCV",
			src: base + "/ui/technologies/opencv.png",
			link: "https://opencv.org/",
		},
		{
			name: "YOLO",
			src: base + "/ui/technologies/yolo.png",
			link: "https://pjreddie.com/darknet/yolo/",
		},
		{
			name: "NumPy",
			src: base + "/ui/technologies/numpy.png",
			link: "https://numpy.org/",
		},
	];
</script>

<PageSection id="technologies-section">
	<div class="technologies-section-right">
		<div class="technologies-section-text">
			<HeaderChip>{$_("home.technologies.chip", defaultI18nValues)}</HeaderChip>
			<h2>{$_("home.technologies.title", defaultI18nValues)}</h2>
			<p>{$_("home.technologies.description", defaultI18nValues)}</p>
		</div>
		<hr />
		<div class="technologies-grid-section">
			<div class="technologies-grid">
				{#each technologies as { name, src, link }, i}
					<a href={link} rel="noopener noreferrer" class="technology-link">
						<img class="technology-image" {src} alt={name} title={name} />
					</a>
				{/each}
			</div>
		</div>
	</div>
</PageSection>

<style lang="scss">
	@use "TechnologiesSection";
</style>
