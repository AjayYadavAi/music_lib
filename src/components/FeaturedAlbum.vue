<template>
	<!-- featured abbum -->
	<div class="featured pad" id="featuredalbum">
		<div class="container">
			<!-- default heading -->
			<div class="default-heading">
				<!-- heading -->
				<h2>Featured Album</h2>
			</div>
			<!-- featured album elements -->
			<div class="featured-element">
				<div class="row">
					<div class="col-md-4 col-sm-6" v-for="album in musiclist" :key="album.id">
						<!-- featured item -->
						<div class="featured-item ">
							<!-- image container -->
							<div class="figure" v-if="albumImage(album.id)">
								<!-- image -->
								{{ albumImage(album.id) }}
								<img class="img-responsive" :src="albumImage(album.id)" alt="" />
								<!-- paragraph -->
								<p>There are many variations of passages available, but the majority have suffered Lorem alteration in some form, by injected look even slightly believable.</p>
							</div>
							<!-- featured information -->
							<div class="featured-item-info">
								<!-- featured title -->
								<h4>{{ album.name }}</h4>
								<!-- horizontal line -->
								<hr />
								<!-- some responce from social medial or web likes -->
								<p>1024+ <span class="label label-theme">Like</span> &nbsp;&nbsp; 825+ <span class="label label-theme">Love</span></p>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
	<!-- features end -->
</template>
<script>
	import axios from 'axios'
	export default{
		name:"featuredalbum",
		data(){
			return {
				publicPath: process.env.BASE_URL,
				musiclist:{}
			}
		},
		mounted() {
			this.currentData();
		},
		methods: {
			async currentData(){
				var api = "https://api.napster.com/v2.1/albums/top?limit=6&apikey="+process.env.VUE_APP_API_KEY;
				const res = await fetch(api);
				const data = await res.json();
				this.musiclist = data.albums;
			},
			albumImage(id){
				var api = "https://api.napster.com/v2.1/albums/"+id+"/images?apikey="+process.env.VUE_APP_API_KEY;
				axios.get(api).then((response)=>{
					var path = response.data.images[2].url;
					return path;
				});
			}
		}
	}
</script>