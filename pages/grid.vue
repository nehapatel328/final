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
                <ul class="userWrap">
                  <li
                    v-for="(entry, index) in users"
                    v-if="entry[fkey] === filter || filter === 'All'"
                    :item="entry"
                    :key="index"
                    class="user"
                  >
                    <h2 class="title">{{ entry.name }}</h2>
                    <span class="language">
                      Primary Language: <strong>{{ entry.mainLanguage }}</strong>
                    </span>
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

export default ({

  el: '#app',
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
      .get('https://api.nytimes.com/svc/books/v3/lists/best-sellers/history.json?author=Ted%20Chiang&api-key=omt1RPMVtLZFNDcPmJZ4kL2c3xwtL1IB')
      .then(response => (this.title = response.data))
      .then(res => res.json())
      .then(res => (this.users = res))
      .catch(error => {
        console.error(error)
        this.errored = true
      })
      .finally(() => this.loading = false)
  }
});
</script>

<style lang="scss">
.userWrap {
  list-style-type: none;
  padding: 2%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  flex-direction: row;
}

.user {
  padding: 10px;
  margin: 1% 0;
  border: 1px solid #ddd;
  border-radius: 3px;
  width: 45%;
  text-align: left;
}

</style>
