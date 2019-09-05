<template>
<div id="app">
  <ul class="list-unstyled">
    <li class="media">
      <div class="media-body">
        <h5 class="mt-0 mb-1">Bestsellers with Rainbow in the Title</h5>
        <p>{{info}}</p>
        <p v-for="title in titles" :title-index="$index" :title-name="title.name" :title-status="title.status">
        </p>



      </div>
      <img src="~/assets/bookone.jpg" class="img-fluid" style="width:500px;height:400px;" alt="bookshelves">
      <!--Image link:https://flic.kr/p/2985GN5-->
    </li>

    <li class="media">
      <div class="media-body">
        <h5 class="mt-0 mb-1">Bestsellers with Zombie in the Title</h5>
        <p>Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue
          felis
          in faucibus.</p>
      </div>
      <img src="~/assets/bookthree.jpg" class="img-fluid" style="width:500px;height:400px;" alt="bookshelves">
      <!--Image link:https://flic.kr/p/dtwiTY-->
    </li>

    <li class="media">
      <div class="media-body">
        <h5 class="mt-0 mb-1">Bestseller with Nerd in the Title</h5>
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
import axios from 'axios';

export default ({
  el: '#app',

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

  mounted() {
    axios
      .get('https://api.nytimes.com/svc/books/v3/lists/best-sellers/history.json?title=rainbow&api-key=omt1RPMVtLZFNDcPmJZ4kL2c3xwtL1IB')
      .then(response => (this.info = response.data))
      .catch(error => {
        console.error(error)
        this.errored = true
      })
      .finally(() => this.loading = false)
  }
})
</script>

<style lang="scss">
.media {
    padding-bottom: 5%;
}

#app {
    padding: 5%;
    display: flex;
}
</style>
