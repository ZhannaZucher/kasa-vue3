<script setup>
    defineProps({
    accommodation: {
        type: Object,
        required: true
    },
    })
</script>

<template>
	<RouterLink :to="{name: 'accommodation', params: {id: accommodation.id}}" >
		<article class="accommodation-card">
		<div class="accommodation-card__view">
			<img :src="accommodation.cover" alt="logement" />
		</div>
		<h2 class="accommodation-card__label">{{accommodation.title}}</h2>
		</article>
	</RouterLink>
</template>

<style scoped>
    .accommodation-card {
	max-width: 340px;
	height: 340px;
	position: relative;
}
.accommodation-card__view::before {
	content: "";
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	z-index: 1;
	border-radius: 10px;
	background: linear-gradient(180deg, rgba(255, 255, 255, 0) 0%, rgba(0, 0, 0, 0.5) 100%);
}
.accommodation-card__view {
	width: 100%;
	height: 100%;
	position:relative;
	
}
.accommodation-card__view img {
	width: 100%;
	height: 100%;
	object-fit: cover;
	border-radius: 10px;
}
.accommodation-card__label {
	position: absolute;
	color: #fff;
	bottom: 20px;
	left: 20px;
	z-index: 2;
	width: 70%;
	font-weight: 500;
	line-height: 25px;
	font-size: 1em;
}

/*Responsive*/
@media screen and (max-width: 576px) {
	.accommodation-card {
		max-width: 335px;
		height: 255px
	}
}
</style>