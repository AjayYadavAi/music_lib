<template>
	<div class="playlist-content">
		<ul class="list-unstyled">
			<li class="playlist-number" v-for="music in musiclist" :key="music.id">
				<!-- song information -->
				<div class="song-info">
					<h4>{{ music.name }}</h4>
					<p><strong>Album</strong>: {{ music.artistName}} &nbsp;|&nbsp; <strong>Type</strong>: {{ music.type}} &nbsp;|&nbsp; <strong>Singer</strong>: {{ music.artistName}}</p>
				</div>
				<!-- music icon -->
				<div class="music-icon">
					<audio controls class= "audio">
						<source :src="music.previewURL" type="audio/mpeg">
					</audio>
				</div>
				<div class="clearfix"></div>
			</li>

		</ul>
	</div>
</template>
<script>
	export default{
		name:"MusicList",
		props:['musiclist'],
		data(){
			return {

			}
		}
	}
</script>