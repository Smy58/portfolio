<template>
	<div class="slider-card">
		<img :src="item.image" alt="" class="slider-card__img">
		<div class="slider-card__content">
			<p class="slider-card__tech">{{ item.text }}</p>
			<h4 class="slider-card__title">{{ item.title }}</h4>
			<a :href="item.url" class="slider-card__link" target="_blank">View project <img :src="arrowImg" alt="arrow"></a>
		</div>
	</div>
</template>

<script>
import arrow from '@/assets/Slider/arrow.svg'

export default {
	setup() {
		
	},
	props: {
		item: Object
	},
	data() {
		return {
			arrowImg: arrow
		}
	}
}
</script>

<style lang="scss">
	.slider-card {
		width: 486px;
		height: 488px;
		display: flex;
		flex-direction: column;

		background: black;

		&__img {
			width: 486px;
			height: 305px;
		}

		&__content {
			display: flex;
			flex-direction: column;
			padding: 32px;
			
		}

		&__tech {
			text-align: left;
			font-weight: bold;
			font-size: 14px;
			letter-spacing: 4px;
			color: #5ADD4F;
			margin: 0;
			margin-bottom: 17px;
		}

		&__title {
			text-align: left;
			font-weight: bold;
			font-size: 24px;
			color: white;
			margin: 0;
			margin-bottom: 22px;
		}

		&__link {
			text-align: left;
			color: white;
			text-decoration: none;
			display: flex;
			align-items: center;

			gap: 20px;
		}
	}

	@media screen and (max-width: 1200px) {
		.slider-card {
			width: 373px;
			height: 418px;

			&__img {
				width: 373px;
				height: 234px;

			}

			&__content {
				padding: 20px;
			}
		}
		
	}

	@media screen and (max-width: 500px) {
		.slider-card {
			width: 300px;
			height: 348px;

			&__img {
				width: 300px;
				height: 188px;
			}

			&__content {
				padding: 14px;
			}

			&__tech {
				font-size: 10px;
				margin-bottom: 10px;
			}

			&__title {
				font-size: 20px;
			}

			&__link {
				font-size: 14px;
			}
		}
	}
</style>