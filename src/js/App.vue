<template>
	<div>
		<!-- Introduction -->
		<section class="section">
			<div class="container">
				<div class="columns is-vcentered">
					<!-- Column -->
					<div class="column">
						<section class="section zero-top-padding">
							<div class="level">
								<div class="level-left">
									<div class="level-item">
										<div class="field has-addons social-icons">
											<span class="has-tooltip-arrow has-tooltip-bottom" data-tooltip="Github"><a class="color-bluee" href="https://github.com/kotnikd3"><i class="fab fa-github fa-3x"></i></a></span>
											<span class="has-tooltip-arrow has-tooltip-bottom" data-tooltip="Goodreads"><a href="https://www.goodreads.com/user/show/103410209-denis-kotnik"><i class="fab fa-goodreads fa-3x"></i></a></span>
											<!-- <span v-show="selectedLang == 'sl'" class="has-tooltip-arrow has-tooltip-bottom" :data-tooltip="'Curriculum Vitae (' + selectedLang + ')'"><a :href="cvSl"><i class="far fa-address-card fa-3x"></i></a></span> -->
										</div>
									</div>
								</div>
								<div class="level-right">
									<div class="level-item">
										<div class="field has-addons">
											<p class="control">
												<button @click="toggleClass('sl')" :class="['button', { 'is-link' : selectedLang == 'sl' }]">SL</button>
											</p>
											<p class="control">
												<button @click="toggleClass('en')" :class="['button', { 'is-link' : selectedLang == 'en' }]">EN</button>
											</p>
											<p class="control">
												<button @click="toggleClass('nl')" :class="['button', { 'is-link' : selectedLang == 'nl' }]">NL</button>
											</p>
										</div>
									</div>
								</div>
							</div>
						</section>
						
						<section class="section">
							<h1 class="title">Denis Kotnik</h1>
							<h2 class="subtitle" v-text="about[selectedLang]"></h2>
							<p v-html="introduction[selectedLang]"></p>
						</section>
				 	</div>
					<!-- Column -->
				 	<div class="column has-text-centered">
						<img :src="imageDenis" alt="Denis Kotnik">
					</div>
				</div>
			</div>
		</section>
		<!-- Opinions -->
		<section v-show="selectedLang == 'sl'" class="section zero-top-padding">
			<div class="container">
				<div class="section">
					<h1 class="title is-4">O mnenjih in resnici</h1>
					<p v-html="opinions[selectedLang]"></p>
				</div>
			</div>
		</section>
		<!-- Philosophy -->
		<section v-show="selectedLang == 'sl'" class="section zero-top-padding">
			<div class="container">
				<div class="section">
					<h1 class="title is-4">O potrebi po filozofiji</h1>
					<div class="columns">
						<div class="column is-two-thirds">
							<p v-html="philosophy[selectedLang]"></p>
						</div>
						<div class="column has-text-centered">
							<img :src="imagePhilosophy" alt="Denis Kotnik">
						</div>
					</div>
				</div>
			</div>
		</section>
		<!-- Capitalism -->
		<section v-show="selectedLang == 'sl'" class="section zero-top-padding">
			<div class="container">
				<div class="section">
					<h1 class="title is-4">Filozof proti kapitalizmu</h1>
						<p v-html="capitalism[selectedLang]"></p>
				</div>
			</div>
		</section>
		<!-- Loneliness vs -->
		<section v-show="selectedLang == 'sl'" class="section zero-top-padding">
			<div class="container">
				<div class="section">
					<h1 class="title is-4">Samota proti osamljenosti</h1>
						<p v-html="loneliness[selectedLang]"></p>
				</div>
			</div>
		</section>
		<!-- Psichotherapy as philosophy-->
		<section v-show="selectedLang == 'sl'" class="section zero-top-padding">
			<div class="container">
				<div class="section">
					<h1 class="title is-4">Psihoterapija kot zastopnica filozofije</h1>
						<p v-html="psichotherapy[selectedLang]"></p>
				</div>
			</div>
		</section>
		<!-- Footer -->
		<footer class="footer">
			<div class="container">
				<div class="content has-text-centered">
					<p class="has-text-grey">Denis Kotnik<span class="icon"><i class="far fa-copyright fa-flip-horizontal"></i></span>2021</p>
				</div>
			</div>
		</footer>
	</div>
</template>

<script>
import { translations } from './Translations.js';

export default {
  data() {
	  // Merge two dictionaries: Object.assign({}, a, b);
	  return Object.assign({}, translations, {
		  selectedLang: 'sl',
		  imageDenis: require('../images/me_2.jpg'),
		  imagePhilosophy: require('../images/philosophy.jpg')
		  //cvSl: require('../Latex_CV_SL/Denis_Kotnik_CV_SL.pdf')
	  });
  },
  methods: {
	toggleClass(lang) {
	  this.selectedLang = lang;
	}
  }
}
</script>