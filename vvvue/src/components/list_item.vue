<template>
	<li>
		<span>
			<strong>Порядковый номер: {{ index + 1 }}</strong>
				<p>Ф.И.О: {{ dior.title }}</p> <p>Дата: {{ dior.date }}</p> <p>Количество отработанных дней: {{ dior.count }}</p> <p>Размер заработной платы сотрудника: {{ dior.payment }} </p> 
				<p>С учётом налога: {{ dior.paymentwWithFee }} </p>
		</span>
		<button class="btn_remove" v-on:click="$emit('remove-item', dior)">Удалить</button>
	</li>
</template>

<script>
export default {

	props: {
		dior: {
			type: Object,
			required: true
		},

		index: Number
	}
}
</script>

<style scoped>
	li {
		border: 1px solid gray;
		display: flex;
		justify-content: space-between;
		padding: .5rem 2rem;
		margin-bottom: 1rem;
	}

	strong {
		padding-right: 0.5rem;
	}

	.btn_remove {
		background: white;
		border: 2px solid blue;
		color: black;
		font-weight: bold;
		max-height: 1.5rem;
		cursor: pointer;
		width: 5rem;
	}

</style>