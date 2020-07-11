<template>
	<div id="latestalbum" class="hero pad">
		<div class="container">
			<div class="hero-content ">
				<h2>Latest Album</h2>
				<hr>
				<p>We sing the best <strong class="theme-color">Songs</strong> and now we control the world best <strong class="theme-color">Music</strong>.</p>
			</div>
			<div class="hero-playlist">
				<div class="row">
					<div class="col-md-6 col-sm-6">
						<div class="figure">
							<img class="img-responsive" :src="`${publicPath}melodi/img/album/1.jpg`" alt="" />
							<img class="img-responsive disk" :src="`${publicPath}melodi/img/album/disk.png`" alt="" />
						</div>
						<div class="album-details">

						</div>
					</div>
					<div class="col-md-6 col-sm-6">
						<music-list v-bind:musiclist="musiclist"></music-list>
					</div>
				</div>
			</div>
		</div>
	</div>
	<!--/ hero end -->
</template>

<script>
	import MusicList from './MusicList'

	export default{
		name:"AlbumDetail",
		components:{ 'music-list':MusicList},
		data(){
			return {
				publicPath: process.env.BASE_URL,
				musiclist:{}
			}
		},
		mounted() {
			this.currentData(this.$route.params.id);
		},
		methods: {
			async currentData(id){
				console.log(id);
				var api = "https://api.napster.com/v2.1/albums/"+id+"/albums/top?apikey="+process.env.VUE_APP_API_KEY;
				const res = await fetch(api);
				const data = await res.json();
				this.musiclist = data.tracks;
			},
		}
	}
</script>