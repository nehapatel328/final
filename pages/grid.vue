<template>
<div id="app">
  <header>
    <h1 slot="header">{{ mainmsg }}</h1>
    <p slot="subtitle">{{ titlemsg }}</p>
  </header>
  <div class="container">
    <div class="row">
      <div class="col-md-auto py-3 px-lg-5 border bg-light row align-items-center mr-auto">
        <b-card no-body class="overflow-hidden" style="max-width: 540px;">
          <b-row no-gutters>
            <b-col md="6">
              <b-card-img src="~/assets/bookfive.jpg" class="img-fluid rounded-0" alt="bookshelves"></b-card-img>
              <!--Image link:https://flic.kr/p/ZG35Kn-->
            </b-col>
            <b-col md="6">
              <b-card-body title="Ted Chiang">
                <b-card-text>
                <ul class="card" v-if="titles">
                  <li
                    v-for="title of titles"
                    :key="title.id"
                    :title="title"
                    class="user"
                  />
                </ul>
                </b-card-text>
              </b-card-body>
            </b-col>
          </b-row>
        </b-card>
      </div>

      <div class="col-md-auto py-3 px-lg-5 border bg-light row align-items-center mr-auto">
        <b-card no-body class="overflow-hidden" style="max-width: 540px;">
          <b-row no-gutters>
            <b-col md="6">
              <b-card-img src="~/assets/booksix.jpg" class="img-fluid rounded-0" alt="bookshelve"></b-card-img>
              <!--Image link:https://flic.kr/p/qef5tT-->
            </b-col>
            <b-col md="6">
              <b-card-body title="Jhumpa Lahiri">
                <b-card-text>
                  <ul>
                    <li>Title: {{ title }}</li>
                    <li>Publisher: {{ publisher }}</li>
                    <li>Rank: {{ ranks_history }}</li>
                    <li>Isbns: {{ isbns }}</li>
                    <li>Description: {{ description }}</li>
                  </ul>
                </b-card-text>
              </b-card-body>
            </b-col>
          </b-row>
        </b-card>
      </div>
    </div>
    <!--close row-->

    <div class="row">
      <div class="col-md-auto py-3 px-lg-5 border bg-light row align-items-center mr-auto">
        <b-card no-body class="overflow-hidden" style="max-width: 540px;">
          <b-row no-gutters>
            <b-col md="6">
              <b-card-img src="~/assets/bookseven.jpg" class="img-fluid rounded-0" alt="bookshelves"></b-card-img>
              <!--Image link:https://flic.kr/p/Cm9pC-->
            </b-col>
            <b-col md="6">
              <b-card-body title="Stephen King">
                <b-card-text>
                  <ul>
                    <li>{{ title }}</li>
                    <li>{{ publisher }}</li>
                    <li>{{ ranks_history }}</li>
                    <li>{{ isbns }}</li>
                    <li>{{ description }}</li>
                  </ul>
                </b-card-text>
              </b-card-body>
            </b-col>
          </b-row>
        </b-card>
      </div>

      <div class="col-md-auto py-3 px-lg-5 border bg-light row align-items-center mr-auto">
        <b-card no-body class="overflow-hidden" style="max-width: 540px;">
          <b-row no-gutters>
            <b-col md="6">
              <b-card-img src="~/assets/bookeight.jpg" class="img-fluid rounded-0" alt="bookshelves"></b-card-img>
              <!--Image link:https://flic.kr/p/21TG4zA-->
            </b-col>
            <b-col md="6">
              <b-card-body title="Toni Morrison">
                <b-card-text>
                  <ul>
                    <li>{{ title }}</li>
                    <li>{{ publisher }}</li>
                    <li>{{ ranks_history }}</li>
                    <li>{{ isbns }}</li>
                    <li>{{ description }}</li>
                  </ul>
                </b-card-text>
              </b-card-body>
            </b-col>
          </b-row>
        </b-card>
      </div>
    </div>
    <!--close row-->

  </div>
</div>
<!--close container-->
</template>

<script>
const url = 'https://api.nytimes.com/svc/books/v3'
import title from '~/components/title.vue';
import axios from "axios";

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
      loading: true,
      titles: null,
        errored: false
      }
    },
    components: {
    title
    },

    data: function() {
    return {
      title: null,
      loading: true,
      mainmsg: 'Authors',
      titlemsg: 'Learn about bestselling authors',
      errored: false
    }
  },
  mounted() {
    axios
      .get('https://api.nytimes.com/svc/books/v3/lists/best-sellers/history.json?api-key=omt1RPMVtLZFNDcPmJZ4kL2c3xwtL1IB')
      .then(response => (this.title = response.data))
      .then(response => (this.description = response.data))
      .then(res => res.json())
      .then(res => (this.title = res))
      .catch(error => {
        console.error(error)
        this.errored = true
      })
      .finally(() => this.loading = false)
  }
});
</script>

<style lang="scss">


</style>
