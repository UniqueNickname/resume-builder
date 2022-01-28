<template>
<ul class="space-y-2">
	<li v-for="[key, value] in Object.entries(options)" :key="key">
		<span class="text-opacity-50 text-black mr-2">{{ key }}:</span>
		<ul v-if="Array.isArray(value)" class="ml-2 space-y-2 pr-20">
			<li v-for="(item, index) in value" :key="item">
				- {{ item }}<template v-if="index !== value.length - 1">;</template><template v-else>.</template>
			</li>
		</ul>
		<span v-else>{{ value }}</span>
	</li>
</ul>
</template>

<script setup lang="ts">
interface Props {
	options: { [key: string]: string | string[] }
}

defineProps<Props>()
</script>