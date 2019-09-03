<template>
<div role="tablist">
  <b-card no-body class="mb-1">
    <b-card-header header-tag="header" class="p-1" role="tab">
      <b-button block href="#" v-b-toggle.accordion-1 variant="info">Accordion 1</b-button>
    </b-card-header>
    <b-collapse id="accordion-1" visible accordion="my-accordion" role="tabpanel">
      <b-card-body>
        <b-card-text>I start opened because <code>visible</code> is <code>true</code></b-card-text>
        <b-card-text>{{ text }}</b-card-text>
      </b-card-body>
    </b-collapse>
  </b-card>

  <b-card no-body class="mb-1">
    <b-card-header header-tag="header" class="p-1" role="tab">
      <b-button block href="#" v-b-toggle.accordion-2 variant="info">Accordion 2</b-button>
    </b-card-header>
    <b-collapse id="accordion-2" accordion="my-accordion" role="tabpanel">
      <b-card-body>
        <b-card-text>{{ text }}</b-card-text>
      </b-card-body>
    </b-collapse>
  </b-card>

  <b-card no-body class="mb-1">
    <b-card-header header-tag="header" class="p-1" role="tab">
      <b-button block href="#" v-b-toggle.accordion-3 variant="info">Accordion 3</b-button>
    </b-card-header>
    <b-collapse id="accordion-3" accordion="my-accordion" role="tabpanel">
      <b-card-body>
        <b-card-text>{{ text }}</b-card-text>
      </b-card-body>
    </b-collapse>
  </b-card>
</div>
</template>

<script>
//key: 9fuidq7Hi2xA7tbWcwm6yg and secret: OU4YIn6T27PY35KVUQRi5hAKAmemPM2hYwPBvY4Bg
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
  .my-accordion {
  display: inline-block;
    display: flex;
    justify-content:space-around;
    cursor: pointer;
    &:hover {
      background: red;
    }
  }
</style>
