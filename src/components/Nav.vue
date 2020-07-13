<template>
	<header>
		<nav class="secondary-menu">
			<div class="container">
				<div class="sm-left">
					<strong>Phone</strong>:&nbsp; <a href="#">555 555 555</a>&nbsp;&nbsp;&nbsp;&nbsp;
					<strong>E-mail</strong>:&nbsp; <a href="/">music.site@melodi.com</a>
				</div>
				<div class="sm-right">
					<div class="sm-social-link">
						<a class="h-facebook" href="#"><i class="fa fa-facebook"></i></a>
						<a class="h-twitter" href="#"><i class="fa fa-twitter"></i></a>
						<a class="h-google" href="#"><i class="fa fa-google-plus"></i></a>
						<a class="h-linkedin" href="#"><i class="fa fa-linkedin"></i></a>
					</div>
				</div>
				<div class="clearfix"></div>
			</div>
		</nav>
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