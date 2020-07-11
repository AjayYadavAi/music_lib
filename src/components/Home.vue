<template>
	<div id="home">
		<Banner></Banner>
		<LatestAlbum></LatestAlbum>
		<FeaturedAlbum></FeaturedAlbum>
	</div>
</template>
<script>
import Banner from './Banner.vue'
import LatestAlbum from './LatestAlbum.vue'
import FeaturedAlbum from './FeaturedAlbum.vue'
	export default{
		name:"home",
		components:{
			Banner,
			LatestAlbum,
			FeaturedAlbum
		}

	}
</script>