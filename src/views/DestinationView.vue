<template>
	<section class="destination-section bg-style">
		<div class="destination-content">
			<h3><span>01 </span>Pick your destination</h3>

			<swiper
				:modules="modules"
				:slides-per-view="1"
				:space-between="100"
				:pagination="pagination"
				class="d-flex justify-content-between align-items-center"
			>
				<swiper-slide
					v-for="(dest, index) in destinations"
					:key="index"
					class="d-flex justify-content-between align-items-center"
				>
					<div class="select-dest d-flex justify-content-between">
						<div class="dest-img">
							<img class="w-100" :src="dest.images.webp" :alt="dest.name" />
							<!-- <img
								class="w-100"
								src="../assets/img/destination/image-moon.png"
								:alt="dest.name"
							/> -->
						</div>
						<div class="dest-desc">
							<div class="dest-details">
								<h2>{{ dest.name }}</h2>
								<p>
									{{ dest.description }}
								</p>
							</div>
							<div class="dest-stat d-flex align-items-center">
								<div>
									<span class="d-block">AVG. DISTANCE</span>
									<span class="num d-block">{{ dest.distance }}</span>
								</div>
								<div>
									<span class="d-block">Est. travel time</span>
									<span class="num d-block">{{ dest.travel }}</span>
								</div>
							</div>
						</div>
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
		const destinations = json.destinations;
		const destNames = destinations.map((el) => el.name);
		const isActive = false;
		return {
			pagination: {
				clickable: true,
				renderBullet: function (index, className) {
					console.log(destNames, destinations);
					return (
						'<span class="' + className + '">' + destNames[index] + "</span>"
					);
				},
			},
			modules: [Pagination, Scrollbar, A11y],
			isActive,
			destinations,
			destNames,
		};
	},
};
</script>

<style scoped>
.destination-section {
	position: absolute;
	top: 0;
	left: 0;
	padding-top: var(--section-pt);
	background-image: var(--destination-bg);
}
.destination-content {
	width: 80%;
	margin: 0 auto;
	height: 100%;
}
.dest-img {
	max-width: 30%;
}
img {
	width: 100%;
	object-fit: contain;
}
.dest-desc {
	color: var(--white);
	max-width: 50%;
}
.dest-desc ul {
	margin-bottom: 40px;
}

.dest-desc h2 {
	font-size: clamp(56px, 2.4vw, 100px);
	text-transform: capitalize;
}
.dest-desc p {
	font-size: clamp(15px, 2.4vw, 18px);
	color: #d0d6f9;
	padding-bottom: 62px;
	border-bottom: 0.5px solid #383b4b;
	margin-bottom: 30px;
}
.dest-stat div:first-child {
	margin-right: 76px;
}
.dest-stat div span {
	text-transform: uppercase;
}
.dest-stat div span:first-child {
	color: #d0d6f9;
	font-size: 14px;
	margin-bottom: 10px;
}
.dest-stat div span:nth-child(2) {
	color: #ffffff;
	font-size: 28px;
}
@media (max-width: 1025px) {
	.destination-section {
		padding-top: var(--section-pt);
	}
	.select-dest {
		justify-content: center;
		flex-direction: column;
		align-items: center;
	}
	.dest-desc {
		max-width: 100%;
		text-align: center;
	}
	.dest-desc ul,
	.dest-stat {
		justify-content: center;
	}
	.dest-img {
		max-width: 100%;
		margin-bottom: 50px;
	}
	.dest-desc p {
		padding-bottom: 70px;
	}
}
@media (max-width: 768px) {
	.destination-section {
		padding-top: var(--section-pt);
	}
	.select-dest {
		height: unset;
	}
	.dest-img {
		max-width: 70%;
		margin-bottom: 20px;
	}
	.dest-desc p {
		padding-bottom: 30px;
		margin-bottom: 10px;
	}
	.dest-desc ul {
		margin-bottom: 10px;
	}
	.dest-stat {
		flex-direction: column;
	}
	.dest-stat div:first-child {
		margin-right: 0;
		margin-bottom: 20px;
	}
	.dest-desc li {
		margin-right: 10px;
	}
	.dest-desc li.active::after {
		bottom: -5px;
	}
}
</style>
