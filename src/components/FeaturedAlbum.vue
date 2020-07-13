<template>
	<div class="featured pad" id="featuredalbum">
		<div class="container">
			<div class="default-heading">
				<h2>Featured Album</h2>
			</div>
			<div class="featured-element">
				<div class="row">
					<div class="col-md-4 col-sm-6" v-for="(album,index) in musiclist" :key="album.id">
						<router-link :to="`/album/${album.id}`">
							<div class="featured-item ">
								<div class="figure">
									<img class="img-responsive" :src="images[index]" alt="" />
									<p>There are many variations of passages available, but the majority have suffered Lorem alteration in some form, by injected look even slightly believable.</p>
								</div>
								<div class="featured-item-info">
									<h4>{{ album.name }}</h4>
									<hr />
								</div>
							</div>
						</router-link>
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
				musiclist:{},
				images:[]
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

				for(var i=0;i<this.musiclist.length;i++){
					var apiimg = "https://api.napster.com/v2.1/albums/"+this.musiclist[i].id+"/images?apikey="+process.env.VUE_APP_API_KEY;
					axios.get(apiimg).then((response)=>{
						this.images.push(response.data.images[2].url);
					});
				}
			},
		},
	}
</script>