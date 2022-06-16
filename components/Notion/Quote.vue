<script setup>
const props = defineProps(['block'])
</script>

<template>
    <blockquote class="notion-quote">
        <NotionRichText :richText="block.quote.rich_text" />
    </blockquote>
</template>
