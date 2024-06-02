<script setup>
import { RouterLink } from 'vue-router'
</script>
<template>
    <header class="header">
        <RouterLink class="header__log" to="/">
            <img src="@/assets/logo.svg" alt="logo">
        </RouterLink>
        <nav class="header__nav">
            <RouterLink to="/">Home</RouterLink>
            <RouterLink to="/about">About</RouterLink>
        </nav>
    </header>
</template>

<style lang="css" scoped>
.header {
	display: flex;
	margin-top: 3rem;
	height: 68px;
	width: 90vw;
	max-width: 1240px;
	display: flex;
	justify-content: space-between;
	align-items: center;
}

.header__nav {
	margin-bottom: 7px;
}

.header__nav a {
	color: #FF6060;
	font-size: 1.4em;
	font-weight: 500;
	text-decoration: none;
	margin-left: 55px;
}

nav a.router-link-exact-active {
	text-decoration-line: underline;
}

@media screen and (max-width: 768px) {
.header {
	margin-top: 0.9rem;
	}

.header__logo img{
	width: 145px;
	height: 47px;
	}

.header__nav a {
	font-size: 0.75em;
	margin-left: 10px;
	text-transform: uppercase;
	}
}

@media screen and (max-width: 375px) {
	.header__nav a {
		font-size: 0.7em;
		margin-left: 10px;
		text-transform: uppercase;
	}
}
</style>