<script setup>
  import Banner from '@/components/Banner.vue'
</script>

<template>
  <main>
    <Banner>
      <img className="banner__img" src="@/assets/img-about.jpg" alt="mountains" />
    </Banner>
  </main>
</template>

<style scoped>
  .banner__img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    opacity: 0.7;
    border-radius: 25px;
  }
  .about-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-bottom: 200px;
  }
  @media screen and (max-width: 576px) {
	.banner__img {
		border-radius: 10px;
	}
}
</style>
