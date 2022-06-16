<template>
	<main class="max-w-6xl mx-auto p-6 lg:p-0">
		<article class="prose max-w-none py-10">
			<h1 class="text-5xl">Nuxt 3 Notion</h1>
			<p>Render your Notion page with Nuxt</p>
			<p>
				<NuxtLink
					:to="`/page/${config.notionRootPage}`"
					class="btn btn-block lg:btn-md btn-outline gap-2"
				>
					<svg
						xmlns="http://www.w3.org/2000/svg"
						viewBox="0 0 448 512"
						class="w-4 h-4 fill-current"
					>
						<path
							d="M448 336v-288C448 21.49 426.5 0 400 0H96C42.98 0 0 42.98 0 96v320c0 53.02 42.98 96 96 96h320c17.67 0 32-14.33 32-31.1c0-11.72-6.607-21.52-16-27.1v-81.36C441.8 362.8 448 350.2 448 336zM143.1 128h192C344.8 128 352 135.2 352 144C352 152.8 344.8 160 336 160H143.1C135.2 160 128 152.8 128 144C128 135.2 135.2 128 143.1 128zM143.1 192h192C344.8 192 352 199.2 352 208C352 216.8 344.8 224 336 224H143.1C135.2 224 128 216.8 128 208C128 199.2 135.2 192 143.1 192zM384 448H96c-17.67 0-32-14.33-32-32c0-17.67 14.33-32 32-32h288V448z"
						/>
					</svg>
					Go to the documentation &rArr;
				</NuxtLink>
			</p>
			<h2>Component list</h2>
			<table>
				<thead>
					<th>Status</th>
					<th>Component type</th>
					<th>Comment</th>
				</thead>
				<tbody>
					<tr v-for="component in components.sort((a,b) => (a.progress > b.progress) ? -1 : ((b.progress > a.progress) ? 1 : 0))" :key="component.name">
						<td>
							<span
								class="badge"
								:class="{
									'badge-success': component.progress > 60,
									'badge-warning':
										component.progress > 30 &&
										component.progress <= 60,
									'badge-error': component.progress <= 40,
								}"
								max="100"
							>
                            {{component.progress}}%
                            </span>
						</td>
						<td class="font-bold">{{ component.name }}</td>
						<td>{{ component.comment }}</td>
					</tr>
				</tbody>
			</table>
		</article>
	</main>
</template>

<script setup>
const config = useRuntimeConfig();
const components = ref([
	{
		name: "Heading 1",
		progress: 100,
		comment: "",
	},
	{
		name: "Heading 2",
		progress: 100,
		comment: "",
	},
	{
		name: "Heading 3",
		progress: 100,
		comment: "",
	},
	{
		name: "Rich Text",
		progress: 100,
		comment: "",
	},
	{
		name: "To-do list",
		progress: 80,
		comment: "Can't show children to-dos right now",
	},
	{
		name: "Subpage",
		progress: 100,
		comment: "",
	},
	{
		name: "Table",
		progress: 70,
		comment: "Tables are pushing out content while in columns",
	},
	{
		name: "Bullet list",
		progress: 80,
		comment: "Doesn't display children items",
	},
	{
		name: "Numbered list",
		progress: 60,
		comment: "Numbered lists don't get numbered, doesn't display children items",
	},
	{
		name: "Quote",
		progress: 90,
		comment: "Doesn't support large size for now",
	},
	{
		name: "Divider",
		progress: 100,
		comment: "",
	},
	{
		name: "Link to page",
		progress: 0,
		comment: "Not yet implemented",
	},
	{
		name: "Callout",
		progress: 100,
		comment: "",
	},
	{
		name: "Columns",
		progress: 80,
		comment: "Some components (like code blocks) are pushing columns out",
	},
	{
		name: "User mention",
		progress: 80,
		comment: "User get only highlighted",
	},
	{
		name: "Page mentioning",
		progress: 100,
		comment: "",
	},
	{
		name: "Date mentioning / reminder",
		progress: 50,
		comment: "Date isn't getting formated yet",
	},
	{ name: "Emojis", progress: 100, comment: "" },
	{
		name: "Inline equation",
		progress: 50,
		comment: "Inline equations get rendered as block equations for now",
	},
	{ name: "Images", progress: 100, comment: "" },
	{
		name: "Bookmark",
		progress: 0,
		comment: "Trying to find nice iframe npm package",
	},
	{ name: "Video", progress: 0, comment: "Not yet implemented" },
	{ name: "Audio", progress: 0, comment: "Not yet implemented" },
	{ name: "File", progress: 0, comment: "Not yet implemented" },
	{ name: "Databases", progress: 0, comment: "Not yet implemented; hard to implement. Will think about it" },
	{
		name: "Table of contents",
		progress: 70,
		comment: "Doesn't display headings when in a collumn",
	},
	{ name: "Block equation", progress: 100, comment: "" },
	{ name: "Breadcrumb", progress: 0, comment: "Not yet implemented" },
	{ name: "Synced block", progress: 80, comment: "Sometimes synced block doesn't work when you duplicate a page with a synced block in it" },
	{ name: "Toggle headings", progress: 100, comment: "" },
]);
</script>
