<template>
	<section class="destination-section bg-style">
		<div class="destination-content">
			<h2><span>01 </span>Pick your destination</h2>

			<div class="select-dest d-flex justify-content-between f-wrap">
				<div class="dest-img">
					<img
						class="w-100"
						src="../assets/img/destination/image-moon.png"
						alt="moon"
					/>
				</div>
				<div class="dest-desc w-50">
					<div class="dest-options">
						<ul class="d-flex">
							<li>Moon</li>
							<li>Mars</li>
							<li>Europa</li>
							<li>Titan</li>
						</ul>
					</div>
					<div class="dest-details">
						<h3>MOON</h3>
						<p>
							See our planet as you’ve never seen it before. A perfect relaxing
							trip away to help regain perspective and come back refreshed.
							While you’re there, take in some history by visiting the Luna 2
							and Apollo 11 landing sites.
						</p>
					</div>
					<div class="dest-stat d-flex align-items-center">
						<div>
							<span class="d-block">AVG. DISTANCE</span>
							<span class="num d-block">384,400 km</span>
						</div>
						<div>
							<span class="d-block">Est. travel time</span>
							<span class="num d-block">3 days</span>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>
</template>

<script>
export default {
	name: "DestinationView",
};
</script>

<style></style>
