<template>
<!--Jumbotron-->
<div class="jumbotron">
<div class="container-fluid">
	<div class ="row">
		<div class="col-md-6">
		  	<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
				<hr class="my-4"> <!--line-->
				<a class="btn btn-primary btn-lg" href="index.html" role="button">Learn more</a>
  		</div><!--close col-md-9-->
  		<div class="col-md-6">
      <img src="~/assets/booktwo.jpg" class="img-fluid" style="width:500px;height:400px;" alt="bookshelves"><!--Image link:https://flic.kr/p/26wosxB-->
  		</div><!--close col-md-6-->
	</div><!--close row-->
</div><!--close container-->
</div><!--close jumbotron-->

</template>

<script>
export default {

  head: {
    title: process.env.npm_package_name || '',
    props: ['title'],
    meta: [{
        charset: 'utf-8'
      },
      {
        name: 'viewport',
        content: 'width=device-width, initial-scale=1'
      },
      {
        hid: 'description',
        name: 'description',
        content: process.env.npm_package_description || ''
      }
    ],
    link: [{
      rel: 'icon',
      type: 'image/x-icon',
      href: '/favicon.ico'
    }],
    script: [{
        src: 'https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.6/umd/popper.min.js'
      },
      {
        src: 'https://code.jquery.com/jquery-3.3.1.slim.min.js'
      },
      {
        src: 'https://stackpath.bootstrapcdn.com/bootstrap/4.2.1/js/bootstrap.min.js'
      }
    ]
  },

  data() {
    return {
      info: null,
      loading: true,
      errored: false
    }
  },
}
</script>

<style>

</style>
