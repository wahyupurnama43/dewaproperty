<template>
	<div class="container mt-5">
		<div class="row header">
			<div class="col-lg-6 col-12 position-relative">
				<div class="text">
					<h1>Forget Busy Work, Start Next Vacation</h1>
					<p class="mt-3">We provide what you need to enjoy your holiday with family. Time to make another memorable moments.</p>
					<button class="btn btn-primary mt-3">Show Me Now</button>

					<div class="iconic row">
						<div class="i-item col-lg-4 col-4">
							<img src="img/icon2.png" alt="" />
							<p class="mt-1"><span>80,409</span> travelers</p>
						</div>
						<div class="i-item col-lg-4 col-4">
							<img src="img/icon3.png" alt="" />
							<p class="mt-1"><span>80,409</span> travelers</p>
						</div>
						<div class="i-item col-lg-4 col-4">
							<img src="img/icon1.png" alt="" />
							<p class="mt-1"><span>80,409</span> travelers</p>
						</div>
					</div>
				</div>
			</div>
			<div class="col-lg-6 col-12">
				<img src="img/banner.jpg" alt="" class="img-full" />
			</div>
		</div>

		<!-- most picked -->
		<div class="batas-atas title-section">
			<h4 class="">Most Picked</h4>
		</div>

		<div class="row property">
			<div class="col-lg-4 col-sm-12">
				<div class="konten-property" style="background: url('img/home1.jpg'); background-repeat: no-repeat; background-position: center; background-size: cover">
					<div class="price">Rp 350.000 Jt</div>
					<div class="konten-text">
						<h4>Blue Origin Fams</h4>
						<p>Jakarta, Indonesia</p>
					</div>
				</div>
			</div>
			<div class="col-lg-8 col-sm-12">
				<div class="row pb-1">
					<div class="col-lg-6 col-sm-12">
						<div
							class="konten-property-2"
							style="background: url('img/home2.jpg'); background-repeat: no-repeat; background-position: center; background-size: cover"
						>
							<div class="price">Rp 350.000 Jt</div>
							<div class="konten-text">
								<h4>Ocean Land</h4>
								<p>Bandung, Indonesia</p>
							</div>
						</div>
					</div>

					<div class="col-lg-6 col-sm-12">
						<div
							class="konten-property-2"
							style="background: url('img/home3.jpg'); background-repeat: no-repeat; background-position: center; background-size: cover"
						>
							<div class="price">Rp 350.000 Jt</div>
							<div class="konten-text">
								<h4>Stark House</h4>
								<p>Bali, Indonesia</p>
							</div>
						</div>
					</div>
				</div>
				<div class="row pt-3">
					<div class="col-lg-6 col-sm-12">
						<div
							class="konten-property-2"
							style="background: url('img/home4.jpg'); background-repeat: no-repeat; background-position: center; background-size: cover"
						>
							<div class="price">Rp 350.000 Jt</div>
							<div class="konten-text">
								<h4>Vinna Vill</h4>
								<p>Surabaya, Indonesia</p>
							</div>
						</div>
					</div>

					<div class="col-lg-6 col-sm-12">
						<div
							class="konten-property-2"
							style="background: url('img/home5.jpg'); background-repeat: no-repeat; background-position: center; background-size: cover"
						>
							<div class="price">Rp 350.000 Jt</div>
							<div class="konten-text">
								<h4>Bobox</h4>
								<p>Medan, Indonesia</p>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>

		<!-- caraousel -->

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

		<div class="batas-atas title-section">
			<h4 class="">Hotels with large living room</h4>
		</div>

		<Carousel :items-to-show="cacheSize()" id="hideArrowsExample">
			<Slide v-for="slide in 10" :key="slide">
				<div class="carousel__item">
					<img src="img/popular2.jpg" alt="" style="width: 310px" />
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

	{{}}
</template>
<script>
import { defineComponent } from "vue";
import { Carousel, Navigation, Slide } from "vue3-carousel";
import { useScreen } from "vue-screen";
import "vue3-carousel/dist/carousel.css";

export default defineComponent({
	name: "Header",
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
			itemC: "",
			windowWidth: screen.width,
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
	},
});
</script>

<style>
.carousel__item .konten-text-popular {
	margin-left: 15px;
}
.konten-text-popular {
	text-align: left;
	margin-left: 10px;
	margin-top: 10px;
}
.konten-text-popular {
	line-height: 5px;
}
#hideArrowsExample .carousel__prev--in-active,
#hideArrowsExample .carousel__next--in-active {
	display: none;
}
.text h1 {
	width: 80%;
	margin-top: 60px;
	font-weight: 700;
	font-size: 52px;
	line-height: 63px;
}

.text p {
	font-weight: 400;
	font-size: 16px;
	line-height: 170%;
	width: 60%;
}
.text button {
	padding: 8px 24px;
	font-weight: 500;
	transition: all 0.3s ease-in-out;
	box-shadow: 0px 8px 15px rgba(50, 82, 223, 0.3);
	border-radius: 4px;
}
.text button:hover {
	background: #2b47c2 !important;
}
.iconic {
	width: 70%;
	position: absolute;
	bottom: 0;
	left: 10px;
}
.iconic span {
	font-weight: 700;
}
.iconic p {
	width: 100% !important;
}
.title-section h4 {
	font-size: 1.5em;
	font-weight: 700;
	margin-bottom: 30px;
}
@media (max-width: 1399.98px) {
	.text h1 {
		font-size: 40px;
		line-height: 55px;
		margin-top: 0px;
	}
	.konten-property {
		height: 445px;
	}
	.konten-property-2 {
		height: 210px;
	}
	.konten-text {
		bottom: 10px;
		left: 25px;
	}
}
@media (max-width: 1066px) {
	.carousel__item .konten-text-popular {
		margin-left: 20px !important;
	}
}
@media (max-width: 991.98px) {
	.property .pb-1,
	.property .pt-3 {
		padding: 0 !important;
	}
	.konten-property,
	.konten-property-2 {
		margin-bottom: 20px;
		height: 350px;
	}
	.konten-text {
		bottom: 10px;
		left: 25px;
	}
	.header {
		flex-direction: column-reverse;
	}
	.text h1 {
		margin-top: 20px;
		width: 100%;
		text-align: center;
		font-size: 42px;
		line-height: 48px;
	}
	.text p {
		text-align: center;
		font-size: 24px;
		width: 90%;
		margin: 0 auto;
		margin-top: 5px !important;
	}
	.text button {
		font-size: 20px;
		margin: 0 auto;
		display: flex;
		justify-content: center;
		align-items: center;
		align-content: center;
	}
	.iconic {
		margin-top: 40px;
		width: 100%;
		position: relative;
		display: flex;
		justify-content: center;
		align-content: center;
		align-items: center;
		text-align: center;
	}
	.iconic p {
		line-height: 40px;
	}
}

@media (max-width: 575.98px) {
	.konten-property,
	.konten-property-2 {
		margin-bottom: 20px;
		height: 300px;
	}
	.header {
		flex-direction: column-reverse;
	}
	.text h1 {
		margin-top: 20px;
		width: 100%;
		text-align: center;
		font-size: 30px;
		line-height: 43px;
	}
	.text p {
		text-align: center;
		font-size: 16px;
		width: 100%;
		margin-top: 5px !important;
	}
	.text button {
		font-size: 16px;
		margin: 0 auto;
		display: flex;
		justify-content: center;
		align-items: center;
		align-content: center;
	}
	.iconic {
		margin-top: 20px;
		width: 100%;
		position: relative;
		display: flex;
		justify-content: center;
		align-content: center;
		align-items: center;
		text-align: center;
	}
	.iconic p {
		line-height: 20px;
	}
}
</style>
