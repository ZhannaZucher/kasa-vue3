<script setup>
import { computed } from 'vue'
import ActiveStar from '@/assets/star-active.svg'
import InactiveStar from '@/assets/star-inactive.svg'


const props = defineProps({
  scaleValue: {
    type: String,
    required: true
  }
})

const range = [1, 2, 3, 4, 5]

const stars = computed(() => {
    const value = parseInt(props.scaleValue)
  return range.map((rangeElement) => ({
    isActive: value >= rangeElement,
    key: rangeElement
  }))
})
</script>

<template>
    <div class="acc-owner__rating">
        <div 
        v-for="star in stars" 
        :key="star.key" 
        class="acc-owner__rating-item">
        <img 
            :src="star.isActive ? ActiveStar : InactiveStar" 
            alt="star-icon" />
        </div>
    </div>
</template>

<style scoped>
.acc-owner__rating {
	display: flex;
	margin-top: 15px;
}

.acc-owner__rating-item {
	margin-left: 5px;
}

@media screen and (max-width: 576px) {
	.acc-owner__rating-item  {
		margin: 0;
	}

	.acc-owner__rating-item img {
		width: 20px;
		height: 20px;
	}
}
</style>