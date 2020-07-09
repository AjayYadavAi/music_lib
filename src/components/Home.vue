<template>
	<div id="home">
		<Banner></Banner>
		<LatestAlbum></LatestAlbum>
		<FeaturedAlbum></FeaturedAlbum>
	</div>
</template>
<script>
import Banner from './components/Banner.vue'
import LatestAlbum from './components/LatestAlbum.vue'
import FeaturedAlbum from './components/FeaturedAlbum.vue'
	export default{
		name:"home",
		components:{
			Banner,
			LatestAlbum,
			FeaturedAlbum
		}

	}
</script>