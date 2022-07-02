<template>
	<section class="crew-slider bg-style p-absolute">
		<div class="crew-content">
			<h3><span>02 </span>Meet Your Crew</h3>
			<swiper
				:modules="modules"
				:slides-per-view="1"
				:space-between="0"
				:pagination="{ clickable: true }"
				@swiper="onSwiper"
				@slideChange="onSlideChange"
			>
				<swiper-slide
					v-for="(member, index) in crew"
					:key="index"
					class="d-flex crew-card justify-content-between align-items-center"
				>
					<div class="info">
						<span class="d-block">{{ member.role }}</span>
						<h2>{{ member.name }}</h2>
						<p>{{ member.bio }}</p>
						<!-- {{ member.images.png }} -->
					</div>

					<div class="crew-img">
						<img :src="member.images.webp" :alt="member.name" />
						<!-- <img
							src="../assets/img/crew/image-douglas-hurley.png"
							:alt="member.name"
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
		const crew = json.crew;

		return {
			modules: [Pagination, Scrollbar, A11y],
			crew,
		};
	},
};
</script>

<style scoped>
.crew-slider {
	background-image: var(--crew-bg);
	top: 0;
	left: 0;
	overflow-x: hidden;
}

.crew-content {
	padding-top: var(--section-pt);
	width: 80%;
	margin: 0 auto;
	height: 100%;
	/* position: absolute;
	left: 10%;
	bottom: 0; */
}
.crew-content h3 {
	margin-bottom: -50px;
}
.crew-content .crew-img {
	max-width: 50%;
	height: 100%;
}
.crew-img img {
	width: 100%;
	height: 100%;
	object-fit: contain;
}

.crew-content .info {
	width: 40%;
}

.info span {
	font-size: clamp(16px, 2.4vw, 24px);
	color: white;
	opacity: 0.5;
	text-transform: uppercase;
}
.info h2 {
	color: white;
	font-size: clamp(36px, 2.4vw, 56px);
	margin: 10px 0 20px;
	text-transform: uppercase;
}
.info p {
	color: #d0d6f9;
	font-size: clamp(15px, 2.4vw, 18px);
}

@media (max-width: 1025px) {
	.crew-content .d-flex {
		flex-direction: column;
		align-items: center;
		justify-content: end;
	}
	.crew-content .crew-img {
		max-width: 100%;
		height: 60%;
		margin-top: 10%;
	}
	.crew-content .info {
		width: 100%;
		text-align: center;
	}
}
@media (max-width: 768px) {
	.crew-content .d-flex {
		flex-direction: column-reverse;
	}
	.crew-content .crew-img {
		height: 40%;
		margin-top: 0;
	}
	.crew-content .info {
		margin-top: 10%;
	}
}
</style>
