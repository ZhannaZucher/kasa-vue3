<script setup>

</script>

<template>
    <footer class="footer">
      <div class="footer__logo">
        <img src="@/assets/logo.svg" alt="logo" />
      </div>
      <p class="footer__copyright">© 2024 Kasa. All rights reserved</p>
    </footer>
</template>

<style scoped>
.footer {
	width: 100vw;
	height: 200px;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	background-color: #000;
	color: #fff;
	font-size: 1.4em;
	padding: 40px 0 30px;
	position: absolute;
	bottom: 0;
}

.footer__logo img {
	width: 122px;
	height: 40px;
}

.footer__copyright {
	margin: 20px 0 0;
}

@media screen and (max-width: 768px) {
	.footer {
		font-size: 0.7em;
	}
}
</style>