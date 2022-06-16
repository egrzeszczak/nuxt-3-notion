<script setup>
const props = defineProps(["block"]);
const { data: content } = await useFetch(
	`/api/notion/retrieve-block-children/${props.block.id}`
);
</script>

<template>
	<div class="notion-column-list">
		<section
			class="notion-column"
			v-for="column in content.results"
			:key="column.id"
		>
			<NotionPageContent :page_id="column.id" />
		</section>
	</div>
</template>
