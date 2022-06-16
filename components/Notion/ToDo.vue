<script setup>
const props = defineProps(["block"]);
</script>

<template>
	<div class="notion-to-do">
		<label class="notion-to-do-label">
			<input
				type="checkbox"
				v-model="block[block.type].checked"
				class="notion-to-do-checkbox"
			/>
			<span class="notion-to-do-label-text" :class="{'notion-to-do-label-text-checked': block[block.type].checked}">
				<NotionRichText :richText="block[block.type].rich_text" />
			</span>
		</label>
	</div>
</template>

<style>

</style>
