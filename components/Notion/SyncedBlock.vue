<script setup>
const props = defineProps(["block"]);
</script>

<template>
	<div class="notion-synced-block">
		<NotionPageContent :page_id="block.id" />
	</div>
</template>
