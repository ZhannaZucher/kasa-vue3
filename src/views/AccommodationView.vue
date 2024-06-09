<script setup>
import { defineProps } from 'vue'
// import { useRouter } from 'vue-router'
import dataHousing from "@/data/housing.json"
import AccommodationDetails from "@/components/AccomodationDetails.vue";

const props = defineProps(['id'])

const accommodation = dataHousing.find((accommodation) => accommodation.id === props.id)
</script>

<template>
    <main id="main-accommodation">
    <!-- todo: Gallery here -->
        <AccommodationDetails :accommodation="accommodation" />
    </main>
</template>

<style scoped>
#main-accommodation {
	display: flex;
	flex-direction: column;
	align-items: center;
	width: 90vw;
	margin: 20px 0 200px;
}
</style>