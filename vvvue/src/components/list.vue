<template>
	<div>
		<ul>
			<list_item 
				v-for="(dior, i) of items"
				v-bind:dior="dior"
				v-bind:index="i"
				v-on:remove-item="removeItem"
			/>
		</ul>
	</div>
</template>

<script>
import list_item from '@/components/list_item.vue'

export default {
	props: ['items'],

	components: {
		list_item
	},

	methods: {
		removeItem(item) {
			this.$emit('remove-item', item)
		}
	}
}
</script>

<style>
	ul {
		margin: 1.5rem 0 0 0;
		padding: 0;
	}
</style>