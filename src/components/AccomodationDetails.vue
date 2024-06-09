<script setup>
import Collapse from './Collapse.vue';
import Tag from './Tag.vue';

defineProps({
  accommodation: {
    type: Object,
    required: true
  }
})
</script>

<template>
    <section class="acc">
        <div class="acc-about__row">
            <div class="acc-about__column">
                <h1 class="acc-about__label">{{ accommodation.title }}</h1>
                <h2 class="acc-about__location">{{ accommodation.location }}</h2>
                <div class="acc-about__tags">
                    <Tag v-for="tag, index in accommodation.tags" :key="index" :content="tag" />
                </div>
            </div>
            <div class="acc-owner__column">
                <div class="acc-owner__row">
                    <h3 class="acc-owner__name">
                        {{accommodation.host.name.split(" ")[0]}}
                        <br />
                        {{accommodation.host.name.split(" ")[1]}}
                    </h3>
                    <div class="acc-owner__img">
                        <img :src="accommodation.host.picture" :alt="accommodation.host.name" />
                    </div>
                </div>
                <!-- todo Rating here -->
            </div> 
         </div>
        <div class="acc-details">
            <Collapse class="collapsible--accommodation" :title="'Description'">
                <p>{{ accommodation.description }}</p>
        </Collapse>
        <Collapse
            class="collapsible collapsible--accommodation"
            :title="'Equipements'"
          >
            <ul>
                <li v-for="element, index in accommodation.equipments" :key="index">{{ element }}</li>
            </ul>
          </Collapse>
        </div>
    </section>

</template>

<style scoped>

.acc {
	width: 90vw;
	max-width: 1240px;
}

.acc-about__row {
	display: flex;
	justify-content: space-between;
	margin: 30px 0;
}

.acc-about__column {
	display: flex;
	flex-direction: column;
	align-items: flex-start;
}

.acc-about__label {
	font-size: 2em;
	color: #FF6060;
	line-height: 50px;
	font-weight: 500;
}

.acc-about__location, .acc-owner__name {
	font-size: 1.05em;
	color: #FF6060;
	line-height: 25px;
	font-weight: 500;
}
.acc-about__tags {
	margin-top: 20px;
	display: flex;
}

.acc-owner__row {
	display: flex;
	justify-content: flex-end;
}

.acc-owner__name {
	align-self: center;
	margin-right: 10px;
}

.acc-owner__img img {
	height: 64px;
	width: 64px;
	border-radius: 50%;
	object-fit: cover;
	object-position: center;
}

.acc-details {
	display: flex;
	justify-content: space-between;
}

/*Responsive*/

@media screen and (max-width: 768px) {
	.acc-about__row {
		flex-direction: column;
	}
	.acc-about__tags {
		margin-top: 0;
	}
	.acc-owner__column {
		display: flex;
		flex-direction: row-reverse;
		justify-content: space-between;
		margin-top: 10px;
	}
	.acc-owner__rating {
		align-self: center;
	}
	.acc-details {
		flex-direction: column;
	}
}

@media screen and (max-width: 576px) {
	.acc-about__row {
		margin: 16px 0;
	}
	.acc-about__label {
		font-size: 1.05em;
		line-height: 25px;
	}
	.acc-about__location {
		font-size: 0.85em;
	}
	.acc-about__tags {
		flex-wrap: wrap;
	}
	.acc-owner__name {
		font-size: 12px;
		line-height: 17px;
	}
	.acc-owner__img img {
		height: 40px;
		width: 40px;
	}
}
</style>