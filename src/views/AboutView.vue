<template lang="pug">
  div(class="view" id="about-view")
    section-def
      dt(slot="title") About
      dd(slot="desc") 
        p Vuetify.js is a component framework for Vue.js 2. It aims to provide clean, semantic and reusable components that make building your application a breeze. Vuetify.js utilizes Google's <strong><a href="https://material.io/" target="_blank">Material Design</a></strong> design pattern, taking cues from other popular frameworks such as <a href="http://materializecss.com/" target="_blank">Materialize.css</a>, <a href="https://getmdl.io/" target="_blank">Material Design Lite</a>, <a href="http://semantic-ui.com/" target="_blank">Semantic UI</a> and <a href="https://v4-alpha.getbootstrap.com/" target="_blank">Bootstrap 4</a>. <div class="text-xs-center"><router-link class="btn btn--large btn--raised primary white--text cta" to="/quick-start"v-ripple="">Get Started Now <v-icon right>fast_forward</v-icon></router-link></div>
    section
      img(src="~public/doc-images/featured.png" width="100%")
      section-header Features
      v-list(three-line)
        v-container(fluid)
          v-row
            v-col(xs12 lg6)
              v-list-item(class="py-1")
                v-list-tile(tag="div")
                  v-list-tile-avatar
                    v-icon(class="primary white--text") widgets
                  v-list-tile-content
                    v-list-tile-title Frontend Components
                    v-list-tile-sub-title The Vuetify.js core is designed to provide a variety of reusable, plug and play components.
            v-col(xs12 lg6)
              v-list-item(class="py-1")
                v-list-tile(tag="div")
                  v-list-tile-avatar
                    v-icon(class="primary white--text") extension
                  v-list-tile-content
                    v-list-tile-title Vue Semantic Components
                    v-list-tile-sub-title Utilize the power of Vue.js 2 functional components with helper components.
            v-col(xs12 lg6)
              v-list-item(class="py-1")
                v-list-tile(tag="div")
                  v-list-tile-avatar
                    v-icon(class="primary white--text") view_quilt
                  v-list-tile-content
                    v-list-tile-title Prototyping Made Easy
                    v-list-tile-sub-title Prototype your project in no time with easy to understand components.

            v-col(xs12 lg6)
              v-list-item(class="py-1")
                v-list-tile(tag="div")
                  v-list-tile-avatar
                    v-icon(class="primary white--text") phone_android
                  v-list-tile-content
                    v-list-tile-title Made for Mobile
                    v-list-tile-sub-title Applications easily transfer from different orientations and screen sizes.
            v-col(xs12 lg6)
              v-list-item(class="py-1")
                v-list-tile(tag="div")
                  v-list-tile-avatar
                    v-icon(class="primary white--text") add_to_queue
                  v-list-tile-content
                    v-list-tile-title Premade Vue CLI Templates
                    v-list-tile-sub-title Vuetify.js comes with 3 Vue CLI templates, pre-configured with Vuetify, and ready to go.
            v-col(xs12 lg6)
              v-list-item(class="py-1")
                v-list-tile(tag="div")
                  v-list-tile-avatar
                    v-icon(class="primary white--text") open_in_browser
                  v-list-tile-content
                    v-list-tile-title Built with Vue.js Server Side Rendering
                    v-list-tile-sub-title Vuetify.js is ready from installation for SSR based applications and PWA's.

    section
      section-header Ecosystem
      section-text Vuetify.js also comes with a subset of packages to help expedite the prototyping process, add additional functionality and additional components.

      v-list
        v-list-item
          v-list-tile(tag="div")
            v-list-tile-avatar
              v-icon color_lens
            v-list-tile-content
              v-list-tile-title Material Design Color Pack

        v-list-item
          v-list-tile(tag="div")
            v-list-tile-avatar
              v-icon play_arrow
            v-list-tile-content
              v-list-tile-title Vue.js CLI Templates including SSR (server-side rendering)

        v-list-item
          v-list-tile(tag="div")
            v-list-tile-avatar
              v-icon security
            v-list-tile-content
              v-list-tile-title Vuetify.js Admin Components <v-chip label class="green white--text">Coming Soon</v-chip>

    section
      h6 Roadmap
      section-text For information regarding future plans, please visit the official <strong>Roadmap</strong> on <a href="https://github.com/vuetifyjs/vuetify/projects/1" target="_blank">Github</a>.
    section
      h6 Sponsors
      section-text Vuetify.js is proudly sponsored by:
      v-container(fluid)
        v-row
          v-col(xs12)
            a(href="https://www.browserstack.com" target="_blank")
              img(src="~public/doc-images/browser-stack.svg" height="35" alt="browser-stack")
    section
      whats-next(route="/quick-start" text="Quick Start") Select from 3 premade Vuetify vue-cli templates. These packages are based off of the official releases, pre-configured for the <strong>Vuetify.js</strong> package.
</template>

<script>
  export default {
    mounted () {
      this.$emit('view', this.meta())
    },

    preFetch () {
      return this.methods.meta()
    },

    methods: {
      meta () {
        return {
          title: 'Vue.js 2 Component Framework | Vuetify.js',
          h1: 'Vuetify.js',
          description: 'Vuetify.js is a reusable semantic component framework for Vue.js 2. It aims to provide clean, semantic and reusable components.',
          keywords: 'vue, vue 2, vue js, vue.js, material design, vue components, material design components, vuetify, vuetify.js'
        }
      }
    }
  }
</script>

<style lang="stylus">
  #about-view
    .cta
      font-size: 18px
      padding: 2rem 4rem
      margin: 50px auto 40px
</style>
