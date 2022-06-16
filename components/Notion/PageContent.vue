<script setup>
const props = defineProps(["page_id"]);
const { pending, data: content } = useLazyFetch(
	`/api/notion/retrieve-block-children/${props.page_id}`
);
watch(content, (newContent) => {});
</script>

<template>
	<Transition>
		<NotionRender v-if="!pending" :content="content.results" />
	</Transition>
	<Transition>
		<div v-if="pending">
			<Skeleton class="h-64" />
			<Skeleton class="h-32" />
			<Skeleton class="h-64" />
			<Skeleton class="h-24" />
		</div>
	</Transition>
</template>

<style>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.2s ease-in-out;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>