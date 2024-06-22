<template>
	<div class="about" id="about">
		<h2 class="about__title">About me</h2>
		<knowledge />

		<p class="about__text"></p>
	</div>
</template>

<script>
import Knowledge from './Knowledge.vue';
export default {
	setup() {
		
	},
	components: {
		Knowledge
	}
}
</script>

<style lang="scss">
	.about {
		width: 90%;
		display: flex;
		flex-direction: column;
		margin-top: 50px;

		&__title {
			font-size: 38px;
			text-align: center;
			margin: 0;

			margin-bottom: 40px;
		}
	}
</style>