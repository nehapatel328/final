<template>
<div class="container" id="app">
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
                <ul>
                  <li></li>
                  <li></li>
                  <li></li>
                  <li></li>
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
            <b-card-img src="~/assets/booksix.jpg" class="img-fluid rounded-0" alt="bookshelves"></b-card-img>
            <!--Image link:https://flic.kr/p/qef5tT-->
          </b-col>
          <b-col md="6">
            <b-card-body title="Jhumpa Lahiri">
              <b-card-text>
                <ul>
                  <li></li>
                  <li></li>
                  <li></li>
                  <li></li>
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
            <b-card-body title="Jane Austen">
              <b-card-text>
                <ul>
                  <li></li>
                  <li></li>
                  <li></li>
                  <li></li>
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
                  <li></li>
                  <li></li>
                  <li></li>
                  <li></li>
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
<!--close container-->
</template>

<script>
export default {
  head: {
    titleTemplate: '%s - Nuxt.js',
    meta: [{
        charset: 'utf-8'
      },
      {
        name: 'viewport',
        content: 'width=device-width, initial-scale=1'
      },

      // hid is used as unique identifier. Do not use `vmid` for it as it will not work
      {
        hid: 'description',
        name: 'description',
        content: 'Meta description'
      }
    ]
  }
}
</script>

<style lang="scss">

</style>
