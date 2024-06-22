<template>
	<div class="knowledge">
		

		<div class="knowledge__content knowledge__content_experience">
			<h3 class="knowledge__subtitle">💼 Work Experience</h3>
			<div class="knowledge__item">
				<h4 class="knowledge__item-title">Rocket Firm</h4>
				<div class="knowledge__item-content">
					<p class="knowledge__item-text">Frontend developer</p>
					<p class="knowledge__item-date">• Aug 2022 - Apr 2023</p>
				</div>
				<p class="knowledge__item__describe">Crete more 15 pages and 50 Web presentations</p>
			</div>

			<div class="knowledge__item">
				<h4 class="knowledge__item-title">Arcana inc.</h4>
				<div class="knowledge__item-content">
					<p class="knowledge__item-text">Frontend developer</p>
					<p class="knowledge__item-date">• Jul 2022 - Aug 2022</p>
				</div>
				<p class="knowledge__item__describe">Working on project with React/Redux</p>
			</div>

			<div class="knowledge__item">
				<h4 class="knowledge__item-title">Freelance</h4>
				<div class="knowledge__item-content">
					<p class="knowledge__item-text">Frontend developer</p>
					<p class="knowledge__item-date"></p>
				</div>
				<p class="knowledge__item__describe">More than 10 SPA and SSR projects</p>
			</div>

			
		</div>

		<div class="knowledge__content knowledge__content_education">
			<h3 class="knowledge__subtitle">📚 Education</h3>
			<div class="knowledge__item">
				<h4 class="knowledge__item-title">Suleyman Demirel University </h4>

				<div class="knowledge__item-content">
					<p class="knowledge__item-text">Bachelor of Information Systems</p>
					<p class="knowledge__item-date">• 2019-Present</p>
				</div>
			</div>

			<div class="knowledge__item">
				<h4 class="knowledge__item-title">Yandex Practicum</h4>

				<div class="knowledge__item-content">
					<p class="knowledge__item-text">Frontend Developer</p>
					<p class="knowledge__item-date">• Jan 2022</p>
				</div>
			</div>
			
		</div>
	</div>
</template>

<script>
export default {
	setup() {
		
	},
}
</script>

<style lang="scss">
	.knowledge {
		width: 100%;
		display: flex;
		justify-content: center;
		gap: 50px;

		&__subtitle {
			text-align: left;
			font-size: 26px;
			margin: 0;
			margin-bottom: 85px;
		}

		&__item {
			display: flex;
			flex-direction: column;
			align-items: start;
			border-bottom: solid 1px #E5E5E5;
			margin-bottom: 35px;
			height: 122px;

			&__describe {
				font-size: 16px;
				margin: 0;
				text-align: left;

			}

			&-content {
				display: flex;
				flex-direction: row;
				align-items: start;
				justify-content: space-between;
				gap: 10px;
				width: 100%;
				margin-bottom: 10px;

			}

			&-title {
				font-size: 22px;
				font-weight: bold;
				margin: 0;
				margin-bottom: 12px;
			}

			&-text {
				font-size: 12px;

				margin: 0;
				color: #000000ae;
				text-align: left;
			}

			&-date {
				font-size: 12px;
				color: #000000ae;


				margin: 0;
				padding-right: 35px;
			}

		}

		&__content {
			width: 400px;

		}
	}

	@media screen and (max-width: 750px) {
		.knowledge {
			flex-direction: column;
			gap: 30px;

			&__content {
				width: 100%;
			}

			&__subtitle {
				margin-bottom: 55px;
			}

			&__item {


				&-text {
					font-size: 10px;
				}

				&-date {
					font-size: 10px;
					padding-right: 0;
				}
			}
		}
	}
</style>