<script setup>
import { ref, onMounted} from "vue"
import dataHousing from "@/data/housing.json"
import Banner from '@/components/Banner.vue'
import Card from '@/components/Card.vue'

const data = ref(null)

onMounted(() => {
	data.value = dataHousing
})
</script>

<template>
  <main id="main-home">
    <Banner :home="true">
          <img class="banner__img" src="@/assets/img-home.jpg" alt="rocks" />
          <h1 class="banner__title">Chez vous, partout et ailleurs</h1>
    </Banner>
	<section class="housing-content">
			<Card v-for="accommodation in data" :key="accommodation.id" :accommodation="accommodation"  />
	</section>
  </main>
</template>

<style scoped>
#main-home {
	display: flex;
	flex-direction: column;
	align-items: center;
	width: 90vw;
	margin-bottom: 240px;
}
.banner__img {
	width: 100%;
	height: 100%;
	object-fit: cover;
	opacity: 0.7;
	border-radius: 25px;
}
.banner__title {
	position: absolute;
	font-size: 2.75em;
	font-weight: 500;
	color: #fff;
	line-height: 68px;
}
.housing-content {
	background-color: #F6F6F6;
	border-radius: 25px;
	margin: 20px 0 0;
	padding: 50px;
	display: grid;
	grid-template-columns: repeat(3, 1fr);
	justify-items: center;
	row-gap: 50px;
	column-gap: 60px;
}

/*Responsive*/
@media screen and (max-width: 992px) {
	.housing-content {
		grid-template-columns: repeat(2, 1fr);
		column-gap: 50px;
	}
}
@media screen and (max-width: 576px) {
	.housing-content {
		grid-template-columns: repeat(1, 1fr);
		padding: 0;
		margin: 0;
		background-color: #fff;
		row-gap: 20px;
		column-gap: 0;
	}
}
@media screen and (max-width: 576px) {
	.banner__img {
		border-radius: 10px;
	}
	.banner__title {
		font-size: 1.4em;
		line-height: 24px;
		width: 70%;
	}
}
</style>