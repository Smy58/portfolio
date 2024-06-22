<template>
  <div class="home">
	<WelcomeBlockVue />
	<SliderVue />
	<AboutVue />
  </div>
</template>

<script>
import WelcomeBlockVue from '@/components/WelcomeBlock.vue'
import AboutVue from '@/components/About.vue'
import SliderVue from '@/components/Slider.vue'
// @ is an alias to /src


export default {
  name: 'HomeView',
  components: {
    WelcomeBlockVue,
	AboutVue,
	SliderVue
  }
}
</script>

<style lang="scss" scoped>
	.home {
		width: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
</style>
