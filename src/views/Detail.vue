<template>
	<Navbar></Navbar>
	<detail-konten></detail-konten>
	<Footer></Footer>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import DetailKonten from "@/components/DetailKonten.vue";
import Footer from "@/components/Footer.vue";
export default {
	name: "Detail",
	components: {
		Navbar,
		Footer,
		DetailKonten,
	},
};
</script>
