<template>
	<navbar></navbar>
	<Header></Header>
	<Footer></Footer>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";

export default {
	name: "Home",
	components: {
		Navbar,
		Header,
		Footer,
	},
};
</script>
