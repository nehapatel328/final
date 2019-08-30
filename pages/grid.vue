<template>
<div id="app">
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
                <ul id="listOne" class="demo">
                <li v-for="value in object">
                  {{list}}
                </li>
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
import axios from "axios";

new Vue({
  el: '#listOne',
  data: {
    results: []
  },
  mounted() {
    axios.get('https://api.nytimes.com/svc/books/v3/lists/best-sellers/history.json?author=Ted%20Chiang&api-key=omt1RPMVtLZFNDcPmJZ4kL2c3xwtL1IB').then(response => {
      this.title = response.data
    })
  }
});


</script>

<style lang="scss">

</style>
