<script setup>
	definePageMeta({
		layout: "products",
	});

	const { data: products } = await useFetch(
		"https://fakestoreapi.com/products"
	);
</script>

<template>
	<section class="grid grid-cols-4 gap-5">
		<div v-for="product in products">
			<NuxtLink :to="`/products/${product.id}`">
				{{ product.title }}</NuxtLink
			>
		</div>
	</section>
</template>

<style scoped></style>
