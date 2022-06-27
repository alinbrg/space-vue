<template>
	<header>
		<div class="container d-flex justify-content-between align-items-center">
			<div class="logo">
				<a href="#">
					<img class="w-100" src="../assets/img/shared/logo.svg" alt="logo" />
				</a>
			</div>
			<nav>
				<ul class="d-flex justify-content-between align-items-center">
					<li>
						<router-link to="/">
							<span>00 </span>
							<span>HOME</span>
						</router-link>
					</li>
					<li>
						<router-link to="/destination">
							<span>01 </span>
							<span>DESTINATION</span>
						</router-link>
					</li>
					<li>
						<router-link to="/crew">
							<span>02 </span>
							<span>CREW</span>
						</router-link>
					</li>
					<li>
						<router-link to="/technology">
							<span>03 </span>
							<span>TECHNOLOGY</span>
						</router-link>
					</li>
				</ul>
			</nav>
			<div class="burger">
				<img src="../assets/img/shared/icon-hamburger.svg" alt="" />
			</div>
		</div>
	</header>
</template>

<script>
export default { name: "HeaderComp" };
</script>

<style></style>
