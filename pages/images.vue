<template>
<div id="app">
    <ul class="list-unstyled">
      <li class="media">
        <div class="media-body">
          <h5 class="mt-0 mb-1">List-based media object</h5>
          <p>Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue
            felis
            in faucibus.</p>
        </div>
        <img src="~/assets/bookone.jpg" class="img-fluid" style="width:500px;height:400px;" alt="bookshelves">
        <!--Image link:https://flic.kr/p/2985GN5-->
      </li>

      <li class="media my-4">
        <div class="media-body">
          <h5 class="mt-0 mb-1">List-based media object</h5>
          <p>Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue
            felis
            in faucibus.</p>
        </div>
        <img src="~/assets/bookthree.jpg" class="img-fluid" style="width:500px;height:400px;" alt="bookshelves">
        <!--Image link:https://flic.kr/p/dtwiTY-->
      </li>

      <li class="media">
        <div class="media-body">
          <h5 class="mt-0 mb-1">List-based media object</h5>
          <p>Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue
            felis
            in faucibus.</p>
        </div>
        <img src="~/assets/bookfour.jpg" class="img-fluid" style="width:500px;height:400px;" alt="bookshelves">
        <!--Image link:https://flic.kr/p/GAeR9v-->
      </li>
    </ul>
</div>
</template>

<script>
export default {
  head: {
    titleTemplate: '%s - Nuxt.js',
    meta: [
      { charset: 'utf-8' },
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },

      // hid is used as unique identifier. Do not use `vmid` for it as it will not work
      { hid: 'description', name: 'description', content: 'Meta description' }
    ]
  }
}
</script>

<style lang="scss">
.image {}
</style>
