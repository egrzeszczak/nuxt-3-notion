<template>
	<span class="notion-mention"
		><!-- Użytkownik -->
		<span class="notion-mention-user" v-if="mention[mention.type].type == 'user'">
			@{{ mention[mention.type].user.name }}
		</span>

		<!-- Data -->
		<span class="notion-mention-date" v-if="mention[mention.type].type == 'date'">
			<span v-if="mention[mention.type].date.start">{{
				mention[mention.type].date.start
			}}</span>
		</span>

		<!-- Strona -->
		<span v-if="mention[mention.type].type == 'page'">
			<NuxtLink class="notion-mention-page" :to="`/page/${mention.mention.page.id}`"
				>{{ mention.plain_text }} &neArr;</NuxtLink
			>
		</span></span
	>
</template>

<script setup>
const props = defineProps(["mention"]);
</script>

<style>

</style>