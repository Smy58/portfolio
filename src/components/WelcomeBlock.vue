<template>
	<div class="welcome">
		<div class="welcome__content">
			<h2 class="welcome__title"><span class="welcome__title_color">I create websites<br/></span>that you need!</h2>
			<p class="welcome__info">Hello! my name is Ilshat. I'm a front-end developer. I create websites for start-up companies and optimize existing ones.</p>
			<div class="welcome__btns">
				<button class="welcome__btn welcome__btn_about" @click="smoothScrollAbout">About me</button>
				<a @click.prevent="downloadItem" class="welcome__btn welcome__btn_cv">Download CV <img :src="arrowIcon" alt="arrow"></a>
			</div>
		</div>
		<img :src="avaImg" alt="avatar" class="welcome__image">
	</div>
</template>

<script>
import arrow from '@/assets/Welcome/arrow.svg'
import ava from '@/assets/Welcome/ava.png'
import cv from '@/assets/pdf/CV.pdf'

import axios from 'axios';

export default {
	setup() {
		
	},
	data() {
		return {
			arrowIcon: arrow,
			avaImg: ava,
			pdf: cv
		}
	},
	methods: {
		smoothScrollAbout() {
			document.getElementById("about").scrollIntoView();
		},
		downloadItem () {
			axios.get(this.pdf, { responseType: 'blob' })
			.then(response => {
				const blob = new Blob([response.data], { type: 'application/pdf' })
				const link = document.createElement('a')
				link.href = URL.createObjectURL(blob)
				link.download = "CV"
				link.click()
				URL.revokeObjectURL(link.href)
			}).catch(console.error)
		}
	}

}
</script>

<style lang="scss">
	.welcome {
		width: 90%;
		display: flex;
		justify-content: center;
		align-items: center;
		margin-top: 30px;
		margin-bottom: 40px;
		gap: 50px;

		&__image {
			width: 350px;
		}


		&__content {
			display: flex;
			flex-direction: column;
			align-items: start;
			width: 50%;

		}

		&__title {
			font-size: 64px;
			font-weight: bold;
			text-align: left;

			margin: 0;
			margin-bottom: 27px;
			&_color {
				color: #5ADD4F;
			}
		}

		&__info {
			font-size: 18px;
			text-align: left;

			margin: 0;
			margin-bottom: 38px;
		}

		&__btns {
			display: flex;
			flex-direction: row;
			gap: 20px;
		}

		&__btn {
			display: flex;
			border: none;
			background: #000;
			gap: 15px;

			color: white;
			padding: 17px 30px;
			font-size: 16px;
			cursor: pointer;

			&_cv {
				background: transparent;
				color: #000;
			}
		}

	}

	@media screen and (max-width: 1000px) {
		.welcome {


			&__image {
				width: 250px;
				height: 250px;
			}

			&__content {
			}

			&__title {
				font-size: 48px;

			}

			&__info {
				font-size: 14px;
				margin-bottom: 22px;
			}

			&__btns {
				gap: 10px;
			}

			&__btn {
				font-size: 12px;
				padding: 12px 22px;
			}
		}
	}

	@media screen and (max-width: 760px) {
		.welcome {
			flex-direction: column;

			&__image {
				display: none;
			}

			&__content {
				width: 80%;
			}

			&__title {
				font-size: 54px;

			}

			&__info {
				font-size: 18px;
				margin-bottom: 38px;

			}

			&__btns {
				gap: 20px;
			}

			&__btn {
				padding: 17px 30px;
				font-size: 16px;
			}
		}
	}

	@media screen and (max-width: 440px) {
		.welcome {

			&__content {
				width: 100%;
			}
			
			&__btns {
				gap: 10px;
				flex-direction: column;
			}

			&__btn {
				align-items: center;
				justify-content: center;
			}
		}
	
	
	}

</style>