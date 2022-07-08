<template>
	<header>
		<div class="container d-flex justify-content-between align-items-center">
			<div class="logo">
				<a href="#">
					<img class="w-100" src="../assets/img/shared/logo.svg" alt="logo" />
				</a>
			</div>
			<nav :class="isActive ? 'active' : ''">
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
				<img
					@click="showBurgerMenu"
					src="../assets/img/shared/icon-hamburger.svg"
					alt=""
				/>
			</div>
		</div>
	</header>
</template>

<script>
export default {
	name: "HeaderComp",
	data() {
		return {
			isActive: false,
		};
	},
	methods: {
		// `this` refers to the component instance.
		showBurgerMenu(e) {
			console.log(e.target);
			this.isActive = !this.isActive;
			// e.target.src = this.isActive
			// 	? "../assets/img/shared/icon-close.svg"
			// 	: "../assets/img/shared/icon-hamburger.svg";
		},
	},
};
</script>

<style>
.burger {
	display: none;
}
header {
	padding-top: var(--header-mt);
	position: relative;
	z-index: 100;
}
header .logo {
	width: 48px;
	height: 48px;
}
header nav::after {
	content: "";
	width: 55%;
	position: absolute;
	top: 50%;
	left: -50%;
	height: 1px;
	background-color: var(--white);
	opacity: 0.25;
}
header nav {
	padding: 39px 138px 36px 120px;
	background-color: rgba(0, 0, 0, 0.3);
	backdrop-filter: blur(30px);
	position: relative;
}
header nav ul {
	gap: 35px;
}

header nav a {
	color: var(--white);
	font-size: var(--f-16px);
}

header nav .router-link-active {
	position: relative;
}
header nav .router-link-active::after {
	content: "";
	width: 90%;
	height: 3px;
	background-color: var(--white);
	display: block;
	position: absolute;
	bottom: -36px;
}
header nav.active {
	display: block;
	position: absolute;
	right: 0;
	top: 0;
	padding-top: 120px;
	height: 100vh;
}
header nav.active .router-link-active::after {
	display: none;
}
header nav.active ul {
	flex-direction: column;
}
@media (max-width: 1025px) {
	header nav::after {
		display: none;
	}
	header nav {
		padding: 39px 48px;
	}
}
@media (max-width: 768px) {
	header nav {
		display: none;
	}
	.burger {
		display: block;
		z-index: 10;
		position: relative;
	}
	.container {
		max-width: calc(100% - 2 * var(--header-ml));

		margin: auto !important;
	}
	.logo {
		width: 40px;
		height: 40px;
	}
}
</style>
