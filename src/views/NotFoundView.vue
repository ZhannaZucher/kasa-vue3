<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
    <div id="error-content">
      <h1 class="error__title">404</h1>
      <h2 class="error__subtitle">
        Oups! La page que vous demandez n'existe pas.
      </h2>
      <RouterLink to="/">Retourner sur la page d’accueil</RouterLink>
    </div>
</template>

<style scoped>
#error-content {
	color: #FF6060;
	display: flex;
	flex-direction: column;
	justify-content: flex-start;
	align-items: center;
	padding-bottom: 200px;
}

.error__title {
	font-size: 260px;
	font-weight: 700;
	margin: 160px 0 60px;
}

.error__subtitle {
	font-size: 36px;
	font-weight: 500;
	line-height: 51px;
	text-align: center;
}

#error-content a {
	color: #FF6060;
	margin: 180px 0 160px;
	font-size: 1.1em;
	font-weight: 500;
}

@media screen and (max-width: 992px) {
	.error__title {
	font-size: 14.4em;
	}
.error__subtitle {
	width: 90vw;
	font-size: 2em;
	}
}

@media screen and (max-width: 576px) {
	.error__title {
		font-size: 6em;
		margin: 200px 0 10px;
	}
	.error__subtitle {
		width: 70vw;
		font-size: 1.05em;
		line-height: 26px;
	}

	#error-content a {
		font-size: 0.8em;
		margin: 130px 0 230px
	}
}
</style>