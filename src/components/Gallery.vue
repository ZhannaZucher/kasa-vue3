<script setup>
import { ref } from 'vue'
 
const props = defineProps({
    slides: {
        type: Array,
        required: true
    }
})

let currentIndex = ref(0)

const goToPrevious = () => {
    const isFirstSlide = currentIndex.value === 0
    const newIndex = isFirstSlide ? props.slides.length - 1 : currentIndex.value - 1
    return currentIndex.value =newIndex
  }
  const goToNext = () => {
    const isLastSlide = currentIndex.value === props.slides.length - 1
    const newIndex = isLastSlide ? 0 : currentIndex.value + 1
    return currentIndex.value =newIndex
  }
</script>

<template>
   <div class="gallery">
    <img
    v-if="slides.length > 1"
          src="@/assets/arrow-back.svg"
          alt="arrow-left"
          class="gallery__previous"
          @click="goToPrevious"
        />
    <img
    v-if="slides.length > 1"
          src="@/assets/arrow-back.svg"
          alt="arrow-right"
          class="gallery__next"
          @click="goToNext"
        />
    <img
        :src="slides[currentIndex]"
        alt="Accommodation view"
        class="gallery__view"
      />
      <p class="gallery__counter">{{ currentIndex + 1 }} / {{ slides.length }}</p>
   </div>
</template>

<style scoped>
.gallery {
	width: 90vw;
	max-width: 1240px;
	height: 415px;
	position: relative;
}

.gallery__view {
	height: 100%;
	width: 100%;
	object-fit: cover;
	border-radius: 25px;
}

.gallery__previous {
	position: absolute;
	top: 50%;
	transform: translate(0, -50%);
	left: 24px;
	z-index: 1;
	cursor: pointer;
}

.gallery__next {
	position: absolute;
	top: 50%;
	transform: translate(0, -50%) rotate(180deg);
	right: 24px;
	z-index: 1;
	cursor: pointer;
}

.gallery__counter {
	position: absolute;
	bottom: 24px;
	left: 50%;
	transform: translate(-50%, 0);
	z-index: 1;
	color: #fff;
	font-weight: 500;
}

/*Responsive*/

@media screen and (max-width: 768px) {
	.gallery__previous, 
	.gallery__next {
		width: 32px;
	}
}

@media screen and (max-width: 576px) {
	.gallery {
		height: 255px;
	}
	.gallery__previous,
	.gallery__next {
		width: 12px;
	}
	.gallery__counter {
		display: none;
	}
}
</style>