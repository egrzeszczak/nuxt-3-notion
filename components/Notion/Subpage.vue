<template>
	<NuxtLink :to="`/page/${block.id}`" class="notion-subpage">
		<span class="flex items-center gap-2 notion-subpage-text">
			<NotionIcon :icon="header.icon" />
			{{ block.child_page.title }}
			&neArr;</span
		>
	</NuxtLink>
</template>

<script setup>
const props = defineProps(["block"]);
const { data: header } = await useFetch(
	`/api/notion/retrieve-page/${props.block.id}`
);
</script>
