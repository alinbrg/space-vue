<template>
	<section class="destination-section bg-style">
		<div class="destination-content">
			<h3><span>01 </span>Pick your destination</h3>

			<div class="select-dest d-flex justify-content-between">
				<div class="dest-img">
					<img
						class="w-100"
						:src="destinations[0].images.webp"
						:alt="destinations[0].name"
					/>
					<!-- <img
						class="w-100"
						src="../assets/img/destination/image-moon.png"
						:alt="destinations[0].name"
					/> -->
				</div>
				<div class="dest-desc">
					<div class="dest-options">
						<ul class="d-flex">
							<li
								v-for="(destination, index) in destinations"
								:key="index"
								@click="changeInfoOnClick(destination, $event, index)"
							>
								{{ destination.name }}
							</li>
						</ul>
					</div>
					<div class="dest-details">
						<h2>{{ destinations[0].name }}</h2>
						<p>
							{{ destinations[0].description }}
						</p>
					</div>
					<div class="dest-stat d-flex align-items-center">
						<div>
							<span class="d-block">AVG. DISTANCE</span>
							<span class="num d-block">{{ destinations[0].distance }}</span>
						</div>
						<div>
							<span class="d-block">Est. travel time</span>
							<span class="num d-block">{{ destinations[0].travel }}</span>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>
</template>

<script>
import json from "../assets/js/data.json";
export default {
	name: "DestinationView",

	data() {
		return {
			destinations: json.destinations,
			isActive: false,
		};
	},
	methods: {
		changeInfoOnClick(destination, event) {
			let target = event.target;

			console.log(destination, target);
			return destination;
		},
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
.dest-desc li {
	font-size: clamp(14px, 0.24vw, 16px);
	margin-right: 22px;
	text-transform: capitalize;
	position: relative;
	cursor: pointer;
}
.dest-desc li:last-child {
	margin-right: 0;
}
.dest-desc li.active::after {
	content: "";
	width: 80%;
	height: 3px;
	position: absolute;
	bottom: -10px;
	background-color: var(--white);
	left: 0;
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
