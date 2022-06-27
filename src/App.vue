<template>
	<main class="p-relative">
		<HeaderComp />
	</main>
	<router-view />
</template>
<script>
import HeaderComp from "@/components/HeaderComp.vue";
export default {
	name: "App",
	components: {
		HeaderComp,
	},
};
</script>
<style>
@import "./assets/css/style.css";
</style>
