<template>
	<header>
		<nav class="navbar navbar-fixed-top navbar-default">
			<div class="container">
				<div class="navbar-header">
					<button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1">
						<span class="sr-only">Toggle navigation</span>
						<span class="icon-bar"></span>
						<span class="icon-bar"></span>
						<span class="icon-bar"></span>
					</button>
					<a class="navbar-brand" href="/">
						<img class="img-responsive" :src="`${publicPath}melodi/img/logo/logo.png`" alt="" />
					</a>
				</div>

				<div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
					<ul class="nav navbar-nav navbar-right">
						<li><a href="#latestalbum">Album List</a></li>
					</ul>
				</div>
			</div>
		</nav>
	</header>
</template>
<script>
	export default{
		name:"Nav",
		data(){
			return {
				publicPath: process.env.BASE_URL
			}
		}
	}
</script>