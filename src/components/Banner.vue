<script setup>
defineProps({
  home: {
    type: Boolean,
    default: false
  }
})
</script>

<template>
    <div  class="banner" :class="{bannerHome: home}">
        <slot></slot>
    </div>
</template>

<style scoped>
.banner {
	height: 223px;
	width: 90vw;
	max-width: 1240px;
	background: #000;
	margin: 45px auto 30px;
	border-radius: 25px;
	display: flex;
	justify-content: center;
	align-items: center;
	position: relative;
}
@media screen and (max-width: 768px) {
	.banner__title {
		margin-left: 16px;
	}
}
@media screen and (max-width: 576px) {
	.banner {
		margin: 0 0 20px 0;
		border-radius: 10px;
		justify-content: flex-start;
	}
	.bannerHome {
		height: 111px;
	}
}
</style>