<template>
	<section class="technology-section bg-style">
		<div class="tech-content">
			<h3><span>03 </span>SPACE LAUNCH 101</h3>
			<swiper
				:modules="modules"
				:slides-per-view="1"
				:space-between="100"
				:pagination="pagination"
				class="d-flex justify-content-between align-items-center"
			>
				<swiper-slide
					v-for="(tech, index) in technology"
					:key="index"
					class="d-flex tech-card justify-content-between align-items-center"
				>
					<div class="info" style="background-image: url()">
						<span class="d-block">THE TERMINOLOGY…</span>
						<h2>{{ tech.name }}</h2>
						<p>{{ tech.description }}</p>
					</div>

					<div class="tech-img">
						<img :src="tech.images.webp" :alt="tech.name" />
						<!-- <img
							src="../assets/img/technology/image-launch-vehicle-landscape.jpg"
							:alt="tech.name"
						/> -->
					</div>
				</swiper-slide>
			</swiper>
		</div>
	</section>
</template>

<script>
import json from "../assets/js/data.json";
// import Swiper core and required modules
import { Pagination, Scrollbar, A11y } from "swiper";

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";
import "swiper/css/pagination";
import "swiper/css/scrollbar";

// Import Swiper styles
export default {
	components: {
		Swiper,
		SwiperSlide,
	},
	setup() {
		const technology = json.technology;

		return {
			pagination: {
				clickable: true,
				renderBullet: function (index, className) {
					return '<span class="' + className + '">' + (index + 1) + "</span>";
				},
			},
			modules: [Pagination, Scrollbar, A11y],
			technology,
		};
	},
};
</script>

<style scoped>
section {
	background-image: var(--tech-bg);
	position: absolute;
	top: 0;
	left: 0;
}
.technology-section {
	position: absolute;
	top: 0;
	left: 0;
	padding-top: var(--section-pt);
	background-image: var(--destination-bg);
}
.tech-content {
	width: 90%;
	margin-left: auto;
	height: 100%;
}

.tech-img {
	max-width: 50%;
	width: 100%;
	height: 100%;
	flex-shrink: 0;
	margin-left: 5%;
}
.tech-img img {
	width: 100%;
	height: 100%;
	object-fit: cover;
}
.tech-card span {
	color: #d0d6f9;
	font-size: clamp(14px, 2.4vw, 16px);
	margin-bottom: 10px;
}
.tech-card h2 {
	color: white;
	font-size: clamp(24px, 2.4vw, 56px);
	margin-bottom: 10px;
}
.tech-card p {
	color: #d0d6f9;
	font-size: clamp(15px, 2.4vw, 18px);
}
@media (max-width: 1025px) {
	.tech-content {
		width: 100%;
		margin-left: auto;
	}
	h3 {
		padding-left: 50px;
	}
	.tech-img {
		max-width: 100%;
		height: 310px;
		margin-left: 0;
		margin-bottom: 50px;
	}
	img {
		height: auto;
	}
	.info {
		width: 80%;
		text-align: center;
		margin-bottom: 50px;
	}
}
@media (max-width: 768px) {
	h3 {
		padding: 0;
		text-align: center;
	}
	.tech-img {
		height: 200px;
	}
}
</style>
