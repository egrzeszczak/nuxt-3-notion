<script setup>
const route = useRoute();
const { pending, data: page } = useLazyFetch(
	`/api/notion/retrieve-page/${route.params.id}`
);
watch(page, (newPage) => {});
</script>

<template>
	<main class="max-w-6xl mx-auto p-6 lg:p-0">
		<article v-if="!pending" class="prose max-w-none py-12">
			<div class="flex items-center gap-4">
				<div><NotionIcon :icon="page.icon" :large="true"/></div>
				<h1 class="text-5xl p-0 m-0">
					{{
						page.properties.title[page.properties.title.type][0][
							page.properties.title[page.properties.title.type][0]
								.type
						].content
					}}
				</h1>
			</div>
			<NotionPageContent :page_id="route.params.id" />
		</article>
		<article v-else class="prose max-w-none py-10">
			<Skeleton class="h-16" />
			<Skeleton class="h-32" />
			<Skeleton class="h-64" />
			<Skeleton class="h-24" />
		</article>
	</main>
</template>

<style></style>
