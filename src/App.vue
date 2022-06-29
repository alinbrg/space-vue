<template>
	<main>
		<HeaderComp />
		<router-view />
	</main>
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
