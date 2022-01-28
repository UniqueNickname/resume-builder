<template>
<div class="space-y-1">
	<p class="pr-24">
		{{ title }}:
	</p>
	<ul class="space-y-1">
		<li v-for="(task, index) in options" :key="index">
		<span>
			- {{ task }}
			<template v-if="index !== options.length - 1">;</template>
			<template v-else>.</template>
		</span>
		</li>
	</ul>
</div>
</template>

<script setup lang="ts">
interface Props {
	title: string
	options: string[]
}

defineProps<Props>()
</script>