<template lang="pug">
  doc-view(v-bind:doc="doc" id="toolbar")
    component-example(header="With Icons" file="toolbar/1" v-bind:data="example")
    component-example(header="With Items" file="toolbar/2" v-bind:data="example")
    component-example(header="With Dropdown" file="toolbar/3" v-bind:data="example")
    component-example(file="toolbar/4" v-bind:data="example")
    component-example(header="Transparent" file="toolbar/5" v-bind:data="example")
    markup(lang="css")
      |&lt;style&gt;
      |  #navbar-image {
      |    background: url('...') center;
      |    height: 300px;
      |  }
      |&lt;/style&gt;
</template>

<script>
  import ItemProps from '../constants/itemable-props'

  export default {
    data () {
      return {
        doc: {
          title: 'Toolbar',
          desc: 'The <code>v-toolbar</code> component is pivotol to any gui, as it generally is the primary source of site navigation. The toolbar component works great in cojunction with a sidebar for hiding links and presenting an activator to open the sidebar on mobile.',
          props: {
            'v-toolbar': {
              params: [
                [
                  'fixed',
                  'Boolean',
                  'false',
                  'Applies the toolbar--fixed class'
                ]
              ]
            },
            'v-toolbar-item': {
              params: [
                [
                  'disabled',
                  'Boolean',
                  'False',
                  'Disables the item'
                ],
                [
                  'href',
                  'String',
                  'javascript:;',
                  'Sets the href attribute'
                ],
                [
                  'ripple',
                  'Boolean',
                  'False',
                  'Applies the ripple directive'
                ],
                [
                  'router',
                  'Boolean',
                  'False',
                  'Designates the item as a router-link'
                ],
                [
                  'tag',
                  'String',
                  '',
                  'Specifies the tag'
                ]
              ]
            }
          },
          functional: {
            'v-toolbar': {
              params: [
                [
                  'v-toolbar-items',
                  '.toolbar__items'
                ],
                [
                  'v-toolbar-logo',
                  '.toolbar__logo'
                ],
                [
                  'v-toolbar-title',
                  '.toolbar__title'
                ],
                [
                  'v-toolbar-side-icon',
                  '.toolbar__side-icon'
                ]
              ]
            }
          },
          slots: {
            'v-toolbar': {
              default: true
            },
            'v-toolbar-item': {
              default: true
            }
          }
        },
        example: {
          items: [
            { text: 'Link' },
            { text: 'Link' },
            { text: 'Link' }
          ],
          itemsGroup: [
            {
              parent: { text: 'Home', icon: 'home' },
              items: [
                {text: 'Our Services', href: 'javascript:;'},
                {text: 'Contact Us', href: 'javascript:;'},
                {text: 'About Us', href: 'javascript:;'}
              ]
            },
            { text: 'Portfolio', href: 'javascript:;', icon: 'work' }
          ],
          itemsGroupV: [
            {
              parent: { text: 'Apply', icon: 'favorite' },
              items: [
                {text: 'Our Mission', href: 'javascript:;'},
                {text: 'Partners', href: 'javascript:;'},
                {text: 'Join Our Team', href: 'javascript:;'}
              ]
            }
          ],
          dropdown_items: [
            { title: 'Send Feedback' },
            { title: 'Request Help' },
            { title: 'Contact Developer' }
          ]
        }
      }
    },

    mounted () {
      this.$emit('view', this.meta())
    },

    preFetch () {
      return this.methods.meta()
    },

    methods: {
      meta () {
        return {
          title: 'Toolbar Component | Vuetify.js',
          h1: 'Toolbars',
          description: 'Toolbar component for Vuetify Framework',
          keywords: 'vuetify, toolbars, components'
        }
      }
    }
  }
</script>

<style lang="stylus">
  #toolbar
    .toolbar
      height: 64px !important
      margin: 1rem 0
      
  #toolbar-image
    background: url('~public/doc-images/nature.jpg') center center / cover no-repeat
    height: 300px
    width: 100%
    
    .toolbar
      margin: 0
</style>