<script setup>
import { ref } from 'vue'

defineProps({
  title: {
    type: String,
    required: true
  },
})
const isOpen = ref(false)
const toggleCollapse = () => {
    isOpen.value = !isOpen.value
}
</script>

<template>
    <div class="collapsible">
        <button class="collapsible__btn" @click="toggleCollapse">
            <h3 class="collapsible__title">
                {{ title }}
            </h3>
            <img v-if="isOpen" src="@/assets/arrow.svg" alt="arrow-down" class="collapsible__arrow-down"  />
            <img v-else src="@/assets/arrow.svg" alt="arrow-up" class="collapsible__arrow-up"  />
        </button>
        <div v-if="isOpen" class="collapsible__content">
            <slot></slot>
        </div>
    </div>
</template>

<style scoped>
.collapsible {
	width: 71vw;
	max-width: 1240px;
	margin-bottom: 30px;
}

.collapsible__btn {
	width: 100%;
	height: 47px;
	border-radius: 5px;
	background-color: #FF6060;
	display: flex;
	color:#fff;
	justify-content: space-between;
	align-items: center;
	padding: 0 18px
}

.collapsible__title {
	font-weight: 500;
	font-size: 1.4em;
}

.collapsible__arrow-up {
	transform: rotate(180deg);
}

.collapsible__content {
	background-color: #F6F6F6;
	border-radius: 0 0 5px 5px ;
	padding: 36px 20px 20px;
	color: #FF6060;
	font-weight: 400;
	font-size: 1.4em;
	line-height: 34px;
}

/*Styles for Accommodation Page Use*/

.collapsible--accommodation {
	width: 40vw;
	max-width: 582px;
}

.collapsible--accommodation h3, 
.collapsible--accommodation p,
.collapsible--accommodation li {
	font-size: 18px;
	line-height: 25px;
}

/*Responsive*/

@media screen and (max-width: 576px) {
	.collapsible {
		width: 90vw;
		margin-bottom: 20px;
	}

	.collapsible__btn {
		height: 30px;
		padding: 10px;
	}

	.collapsible__arrow-up, .collapsible__arrow-down {
		height: 19px;
		width: 19px;
	}

	.collapsible__title {
		font-size: 0.8em;
	}

	.collapsible__content {
		font-size: 0.8em;
		line-height: 18px;
		padding: 20px 10px;
	}
}

/*Responsive for Accommodation Page Use*/
@media screen and (max-width: 768px) {
	.collapsible--accommodation {
		width: 100%;
	}
}

@media screen and (max-width: 576px) {
	.collapsible--accommodation h3,
	.collapsible--accommodation p,
	.collapsible--accommodation li {
			font-size: 13px;
			line-height: 18px;
		}
}
</style>