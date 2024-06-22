<template>
	<div class="slider">
		<h2 class="slider__title">Portfolio</h2>
		<div class="slider__box">
			

			<swiper
				:modules="modules"
				:loop="true"
				:breakpoints="{
					320: {
						slidesPerView: 1,
						spaceBetween: 20
					},
					920: {
						slidesPerView: 2,
						spaceBetween: 20
					},
					1750: {
						slidesPerView: 3,
						spaceBetween: 20
					},
				}"
				
				@swiper="onSwiper"
				@slideChange="onSlideChange"
			>
				
				<swiper-slide v-for="item in items" :key="item.id">
					<SliderCard :item="item"></SliderCard>
				</swiper-slide>
				
			</swiper>

			
		</div>
		<div class="slider__btns">
			<button @click="onPrev()" class="slider__btn slider__btn_prev"><img :src="prev" alt="prev"></button>
			<button @click="onNext()" class="slider__btn slider__btn_next"><img :src="next" alt="next"></button>
		</div>
	</div>
</template>

<script>
import slider1 from '@/assets/Slider/compas.png'
import slider2 from '@/assets/Slider/rickandmorty.png'
import slider3 from '@/assets/Slider/userstable.png'
import slider4 from '@/assets/Slider/filmweb.png'
import slider5 from '@/assets/Slider/medfront.png'
import slider6 from '@/assets/Slider/arsfront.png'
import prev from '@/assets/Slider/prev.svg'
import next from '@/assets/Slider/next.svg'

import { Navigation, Pagination, Scrollbar, A11y } from 'swiper/modules';
import { Swiper, SwiperSlide } from 'swiper/vue'

import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import 'swiper/css/scrollbar';

import SliderCard from './SliderCard.vue';

export default {
	setup() {
		
	},
	components: {
		Swiper,
		SwiperSlide,
		SliderCard
	},
	data() {
		return {
			items: [
			{
					id: 1,
					image: slider1,
					url: 'https://smy58.github.io/compas/',
					title: 'Compas',
					text: 'GitPage, Vue, Nuxt, Slider'
				},
				{
					id: 2,
					image: slider2,
					url: 'https://smy58.github.io/rickandmorty/',
					title: 'Rick and Morty',
					text: 'GitPage, Vue, Pinia, Work with API'
				},
				{
					id: 3,
					image: slider3,
					url: 'https://github.com/Smy58/userstable',
					title: 'Compas',
					text: 'Git repo, React, Next, CRM, JSONPlaceholder, MUI'
				},
				{
					id: 4,
					image: slider4,
					url: 'https://smy58.github.io/filmweb/',
					title: 'FilmWeb',
					text: 'Git page, Vue, Vuex, Work with API'
				},
				{
					id: 5,
					image: slider5,
					url: 'https://github.com/Smy58/MedFrontend',
					title: 'MedFrontend',
					text: 'Git repo, Vue, Vuex, Work with Backend API'
				},
				{
					id: 6,
					image: slider6,
					url: 'https://github.com/Smy58/ArsFront',
					title: 'ArsFront',
					text: 'Git repo, CRM, Vue, Nuxt, Pinia, Work with Backend API'
				},
			],
			prev: prev,
			next: next
		}
	},
	methods: {
		onNext() {
			const swiper = document.querySelector(".swiper").swiper;
			swiper.slideNext();
		},
		onPrev() {
			const swiper = document.querySelector(".swiper").swiper;
			swiper.slidePrev();
		},
	},
	setup() {
		const onSwiper = (swiper) => {
			console.log(swiper);
		};
		const onSlideChange = () => {
			console.log('slide change');
		};
		return {
			onSwiper,
			onSlideChange,
			modules: [Navigation, Pagination, Scrollbar, A11y],
		};
    },

}
</script>

<style lang="scss">
	.swiper {
		padding: 15px !important;

		&-slide {
			display: flex;
			justify-content: center
		}
	}

	.slider {
		width: 90%;
		display: flex;
		flex-direction: column;
		align-items: center;

		&__title {
			font-size: 38px;
			text-align: center;
			margin: 0;
			margin-bottom: 40px;
		}

		&__box {
			margin-bottom: 26px;
			width: 100%;
			padding: 0 12px;
			box-sizing: border-box;
			position: relative;
		}

		&__btns {
			align-self: flex-end;
			display: flex;
			gap: 7px;
		}

		&__btn {
			width: 54px;
			height: 54px;
			border: none;
			background: #000;

			display: flex;
			align-items: center;
			justify-content: center;
			cursor: pointer;
		}
	}

	@media screen and (max-width: 500px) {
		.slider {

			width: 350px;

			&__btn {
				width: 35px;
				height: 35px;
			}
		}
	}
</style>