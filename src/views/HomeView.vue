<template>
	<section class="main-section p-absolute bg-style">
		<div
			class="d-flex justify-content-between content-container p-absolute main-section-content"
		>
			<div class="space w-50">
				<span>SO, YOU WANT TO TRAVEL TO</span>
				<h1>SPACE</h1>
				<p>
					Let’s face it; if you want to go to space, you might as well genuinely
					go to outer space and not hover kind of on the edge of it. Well sit
					back, and relax because we’ll give you a truly out of this world
					experience!
				</p>
			</div>
			<div class="explore d-flex align-items-center justify-content-center">
				EXPLORE
			</div>
		</div>
	</section>
</template>

<script>
// @ is an alias to /src
export default {
	name: "HomeView",
};
</script>

<style scoped>
.main-section {
	width: 100%;
	height: 100%;
	top: 0;
	left: 0;
	background-image: var(--main-bg);
}
.main-section-content {
	left: 10%;
	bottom: 15%;
	width: 80%;
}
.explore {
	width: var(--explore-size);
	height: var(--explore-size);
	border-radius: 50%;
	background-color: var(--white);
	cursor: pointer;
}
@media (min-width: 1024px) {
	.explore:hover {
		box-shadow: 0 0 0 100px rgba(255, 255, 255, 0.1);
	}
}
.space span {
	color: #d0d6f9;
	font-size: clamp(16px, 2.4vw, 28px);
}
.space h1 {
	font-size: clamp(80px, 2.8vw, 150px);
	color: var(--white);
}
.space p {
	color: #d0d6f9;
	font-size: clamp(15px, 2.4vw, 18px);
}

@media (max-width: 1025px) {
	.main-section-content {
		flex-direction: column;
		align-items: center;
		bottom: 90px;
	}
	.main-section .space {
		width: 90%;
		margin-bottom: 100px;
		text-align: center;
	}
	h1 {
		margin: 20px 0;
	}
	.explore {
		margin-top: 100px;
	}
}
@media (max-width: 768px) {
	.main-section-content {
		bottom: 48px;
	}
	.main-section .space {
		margin-bottom: 0;
	}
	.explore {
		margin-top: 85px;
	}
	h1 {
		margin: 0;
	}
	.content-container {
		padding: 0;
		width: 100%;
		left: 0;
	}
}
</style>
