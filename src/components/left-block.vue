<template>
	<div class="space-y-4">
		<div class="flex items-center justify-center space-x-4">
			<div class="rounded-full border border-black w-3 h-3" />
			<h2 class="font-bold">{{ title }}</h2>
			<div class="rounded-full border border-black w-3 h-3" />
		</div>
		<p v-for="option in options" :key="option">
			{{ option}}
		</p>
	</div>
</template>

<script setup lang="ts">
interface Props {
	title: string
	options: string[]
}

defineProps<Props>()
</script>
