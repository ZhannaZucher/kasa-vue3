<script setup>
defineProps({
  content: {
    type: String,
    required: true
  }
})
</script>

<template>
    <div class="tag">
        <p>{{ content }}</p>
    </div>
</template>

<style  scoped>
.tag {
	height: 25px;
	padding: 0 30px;
	border-radius: 10px;
	background-color: #ff6060;
	display: flex;
	justify-content: center;
	align-items: center;
	color: #fff;
	font-weight: 500;
	font-size: 0.8em;
	margin-right: 10px;
}

@media screen and (max-width: 576px) {
	.tag {
		padding: 0 25px;
		height: 18px;
		border-radius: 5px;
		font-size: 0.5em;
		margin-top: 10px;
	}
}
</style>