<template>
	<div class="container">
		<div class="text-center mt-header">
			<h1>Village Angga</h1>
			<p>Bogor, Indonesia</p>
		</div>

		<div class="img-header">
			<div class="row" :class="Dblock()">
				<div class="col-lg-7">
					<img src="img/detail1.jpg" alt="" style="width: 100%" />
				</div>
				<div class="col-lg-5">
					<div class="row">
						<div class="col-lg-12">
							<img src="img/detail2.jpg" alt="" style="width: 100%; height: 280px; margin-bottom: 10px" />
						</div>
						<div class="col-lg-12">
							<img src="img/detail2.jpg" alt="" style="width: 100%; height: 280px; margin-top: 10px" />
						</div>
					</div>
				</div>
			</div>

			<Carousel :items-to-show="1" id="hideArrowsExample" :class="Dnone()">
				<Slide v-for="slide in 3" :key="slide">
					<div class="carousel__item"><img :src="'img/detail' + slide + '.jpg'" alt="" style="width: 100%; height: 280px" /></div>
				</Slide>

				<template #addons>
					<Navigation />
				</template>
			</Carousel>
		</div>

		<div class="about">
			<div class="row">
				<div class="col-lg-8">
					<h3>About the place</h3>
					<p>
						Minimal techno is a minimalist subgenre of techno music. It is characterized by a stripped-down aesthetic that exploits the use of
						repetition and understated development. Minimal techno is thought to have been originally developed in the early 1990s by Detroit-based
						producers Robert Hood and Daniel Bell.
					</p>

					<p>
						Such trends saw the demise of the soul-infused techno that typified the original Detroit sound. Robert Hood has noted that he and Daniel
						Bell both realized something was missing from techno in the post-rave era.
					</p>

					<p>
						Design is a plan or specification for the construction of an object or system or for the implementation of an activity or process, or the
						result of that plan or specification in the form of a prototype, product or process. The national agency for design: enabling Singapore to
						use design for economic growth and to make lives better.
					</p>
				</div>

				<div class="col-lg-4 d-flex align-items-center justify-content-center">
					<div class="card p-4">
						<div class="card-body text-center">
							<h5>Start Price</h5>
							<h2>Rp 200.000.000,00</h2>
							<button class="btn btn-primary mt-3">Chat Wa</button>
						</div>
					</div>
				</div>
			</div>
		</div>

		<div class="batas-atas title-section">
			<h4 class="">Hotels with large living room</h4>
		</div>

		<Carousel :items-to-show="cacheSize()" id="hideArrowsExample">
			<Slide v-for="slide in 10" :key="slide">
				<div class="carousel__item">
					<img src="img/popular1.jpg" alt="" style="width: 310px" />
					<div class="konten-text-popular">
						<h5>Blue Origin Fams</h5>
						<p>Jakarta, Indonesia</p>
					</div>
				</div>
			</Slide>

			<template #addons>
				<Navigation />
			</template>
		</Carousel>
	</div>
</template>

<script>
import { defineComponent } from "vue";
import { Carousel, Navigation, Slide } from "vue3-carousel";
import { useScreen } from "vue-screen";
export default defineComponent({
	name: "DetailKonten",
	setup() {
		const screen = useScreen();
		return {
			screen,
		};
	},
	components: {
		Carousel,
		Slide,
		Navigation,
	},
	data() {
		return {
			windowWidth: screen.width,
			dNone: "d-none",
			dBlock: "d-flex",
			Noslide: 0,
		};
	},
	mounted() {
		window.onresize = () => {
			this.windowWidth = screen.width;
		};
	},
	methods: {
		cacheSize() {
			if (this.windowWidth > 1400) {
				return (this.Noslide = 4);
			} else if (this.windowWidth > 1200) {
				return (this.Noslide = 3);
			} else if (this.windowWidth > 768) {
				return (this.Noslide = 2);
			} else if (this.Noslide < 768) {
				return (this.Noslide = 1);
			}
		},
		Dnone() {
			if (this.windowWidth <= 800) {
				return (this.dNone = "d-block");
			} else {
				return (this.dNone = "d-none");
			}
		},
		Dblock() {
			if (this.windowWidth > 800) {
				return (this.dBlock = "d-flex");
			} else {
				return (this.dBlock = "d-none");
			}
		},
	},
});
</script>

<style scoped>
button {
	padding: 8px 24px;
	font-weight: 500;
	transition: all 0.3s ease-in-out;
	box-shadow: 0px 8px 15px rgba(50, 82, 223, 0.3);
	border-radius: 4px;
}
button:hover {
	background: #2b47c2 !important;
}
.about {
	margin-top: 3rem;
}
.mt-header {
	margin-top: 4rem;
}
.mt-header h1 {
	font-weight: 700;
}
.mt-header p {
	font-weight: 500;
	color: #b0b0b0;
}
#hideArrowsExample .carousel__prev--in-active,
#hideArrowsExample .carousel__next--in-active {
	display: none;
}
</style>
