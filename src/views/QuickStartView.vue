<template lang="pug">
  div(class="view" id="quick-start-view")
    div
      section-def
        dt(slot="title") Getting Started
        dd(slot="desc") Use one of the Vuetify.js Vue CLI packages <em>(based on the official examples)</em> to get your project started in no time. Vuetify.js supports Vue SSR (server-side rendering), SPA (single page application) and standard HTML pages.

    section
      section-header Manual Install
      section-text To test using Vuetify.js without installing a template from Vue CLI, include the files below into your <code>index</code> file of your application after Vue. Vuetify will automatically install and be ready to use.
      markup(lang="html")
        |&lt;link href='https://fonts.googleapis.com/css?family=Roboto:300,400,500,700|Material+Icons' rel="stylesheet" type="text/css"&gt;
        |&nbsp;
        |&lt;link href="https://unpkg.com/vuetify/dist/vuetify.min.css" rel="stylesheet" type="text/css"&gt;
        |&nbsp;
        |&lt;script src="https://unpkg.com/vue/dist/vue.js"&gt;&lt;/script&gt;
        |&nbsp;
        |&lt;script src="https://unpkg.com/vuetify/dist/vuetify.min.js"&gt;&lt;/script&gt;

      h6 Existing Projects
      section-text If you are wanting to use Vuetify in an existing project, you can install by using npm or yarn. Keep in mind, you will still need to <strong><em>include</em></strong> the above css files as they are not part of the javascript import.
      markup(lang="cli")
        |$  npm install vuetify --save-dev
        |&nbsp;
        |$  yarn add vuetify --dev
      section-text In your index.js, import Vuetify and apply the plugin to Vue.
      markup(lang="js")
        |import Vue from 'vue'
        |import Vuetify from 'vuetify'
        |&nbsp;
        |Vue.use(Vuetify)
    section
      section-header Vue CLI
      section-text Vuetify has 3 pre-made Vue CLI templates, 2 being forked from <a href="#!">official Vue.js templates</a>. They contain small modifications to help you get started with Vuetify even faster. These packages require <code>vue-cli</code>. For more information on vue-cli, visit the official <a href="https://github.com/vuejs/vue-cli" target="_blank">Github</a> repository.
      v-tabs(id="vue-cli" class="z-depth-1" grow icons)
        v-tab-item(ripple slot="activators" href="#simple") Simple HTML
          v-icon accessibility
        v-tab-item(ripple slot="activators" href="#webpack") Webpack
          v-icon web
        v-tab-item(ripple slot="activators" href="#webpack-ssr") Webpack SSR
          v-icon cloud_circle
        v-tab-content(id="simple" slot="content")
          v-card
            v-card-text
              h4 Simple HTML Quick Start
              p This template is intended for users who want to try out Vue.js and Vuetify.js in the most simple way. It contains a basic index.html with no additional functionality. This is useful for developers who want to easily preview the features of the framework.
              markup(lang="cli")
                |$  vue init vuetifyjs/simple
        v-tab-content(id="webpack" slot="content")
          v-card
            v-card-text
              h4 Webpack Quick Start
              p This template is intended for users who are already familiar with Vue/Webpack. It contains a very simple webpack setup and is targetted at developers creating prototype or basic applications.
              markup(lang="cli")
                |$  vue init vuetifyjs/webpack
        v-tab-content(id="webpack-ssr" slot="content")
          v-card
            v-card-text
              h4 Webpack SSR Quick Start
              p This template is for advanced users looking to utilize the new Vue SSR (server-side rendering). Based off of the structure in the Vue.js 2 <a href="https://github.com/vuejs/vue-hackernews-2.0" target="_blank">Hackernews</a> repository. The Vuetify.js SSR template provides next generation functionality for advanced Vue applications.
              markup(lang="cli")
                |$  vue init vuetifyjs/webpack-ssr
      
      h6 NPM Install
      section-text After the vue-cli installation finishes, <kbd>cd</kbd> into your project directory and type <kbd>npm install</kbd>. Alternatively, if you are using Facebook's recently released <a href="https://yarnpkg.com/" target="_blank">yarn package manager</a>, you can simply type <kbd>yarn</kbd>.

      section-text For any other package, type <kbd>npm run dev</kbd> into your console. This will start a <a href="https://nodejs.org/en/" target="_blank">nodejs</a> server locally which can be accessed by navigating to <a href="http://localhost:8080" target="_blank">http://localhost:8080</a> in your browser.
    section
      section-header Theme
      section-text Changing your theme is as easy as updating a few variables in your <code>main.styl</code> file. Navigate to this file, <kbd>src/App.vue</kbd> for webpack and <kbd>src/stylus/main.styl</kbd> for webpack-ssr. The available theme array looks like this:
      markup(lang="stylus")
        |$theme := {
        |   primary: $blue.darken-2
        |   accent: $blue.accent-2
        |   secondary: $grey.darken-3
        |   info: $blue.base
        |   warning: $amber.base
        |   error: $red.base
        |   success: $green.base
        |}
      section-text You can modify any of these properties by typing <code>$theme.attribute</code>. If you want to use a built in color, pick a color from the <router-link to="/css/colors">Colors</router-link> section and update the variable.
    section
      section-header Color Pack
      section-text Vuetify comes pre-built with a Material Design Color Pack (thanks <a href="http://materializecss.com/color.html" target="_blank">Materialize.css</a>) by default. While convenient, this also increases the css export size by ~30kb. This can be disabled in both the webpack and webpack-ssr Vue cli templates.
      div(class="title pt-3 pb-3") Webpack
      section-text Navigate to <kbd>src/App.vue</kbd>. Scroll to the style element and set <code>$color-pack = false</code> above the Vuetify css import.

      div(class="title pt-3 pb-3") Webpack-SSR
      section-text Navigate to <kbd>src/stylus/main.styl</kbd>. At the top of the file, declare <code>$color-pack = false</code>.

    section
      whats-next(route="/server-side-rendering" text="Vue SSR") Now that you have your project setup and ready to go, it's time to start your ssr application with the Vuetify.js <strong>webpack-ssr</strong> template.
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
          title: 'Quick Start | Vuetify.js',
          h1: 'Quick Start',
          description: 'Get started with Vue and Vuetify in no time.',
          keywords: 'vuetify quick start, vuetify templates, server side rendering'
        }
      }
    }
  }
</script>