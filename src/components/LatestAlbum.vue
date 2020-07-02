<template>
	<!-- Hero block area -->
	<div id="latestalbum" class="hero pad">
		<div class="container">
			<!-- hero content -->
			<div class="hero-content ">
				<!-- heading -->
				<h2>Latest Album</h2>
				<hr>
				<!-- paragraph -->
				<p>We sing the best <strong class="theme-color">Songs</strong> and now we control the world best <strong class="theme-color">Music</strong>.</p>
			</div>
			<!-- hero play list -->
			<div class="hero-playlist">
				<div class="row">
					<div class="col-md-6 col-sm-6">
						<!-- music album image -->
						<div class="figure">
							<!-- image -->
							<img class="img-responsive" :src="`${publicPath}melodi/img/album/1.jpg`" alt="" />
							<!-- disk image -->
							<img class="img-responsive disk" :src="`${publicPath}melodi/img/album/disk.png`" alt="" />
						</div>
						<!-- album details -->
						<div class="album-details">
							<!-- title -->
							<h4>Perfect Melodi</h4>
							<!-- composed by -->
							<h5>By Himanshu</h5>
							<!-- paragraph -->
							<p>Lorem Ipsum has been the industry's standard dummy text ever since 1500.</p>
							<!-- button -->
							<a href="#" class="btn btn-lg btn-theme" id="playNowBtn"><i class="fa fa-play"></i>&nbsp; Play Now</a>
						</div>
					</div>
					<div class="col-md-6 col-sm-6">
						<!-- play list -->
						<music-list></music-list>
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
		name:"latestalbum",
		components:{ 'music-list':MusicList},
		data(){
			return {
				publicPath: process.env.BASE_URL
			}
		}
	}
</script>