<template lang="pug">
  main
    div.scout-banner.hero
      article.hero-body.columns
        section.container.has-text-centered.column.is-7-desktop.is-offset-3-desktop.is-9-tablet.is-12-mobile
          h1.is-2.subtitle Solicitações
      div.hero-foot
        breadcrumb
    div.scout-container
      div.container.container-responsive.main-container
        h1.title.is-2 Solicitações
        h2.subtitle.is-4 Solicite ceritificados, recompensas e distintivos
        div.columns.is-multiline
          div.column.is-2.menu-column
            aside.menu
              p.menu-label Solicitar
              ul.menu-list
                li
                  router-link(exact v-bind:to="{name: 'formsBadges'}") Distintivos Especiais
                  router-link(exact v-bind:to="{name: 'formsSower'}") Distintivo de Semeador
                  router-link(exact v-bind:to="{name: 'formsRewards'}") Condecorações e Recompensas
                  router-link(exact v-bind:to="{name: 'formsLevel'}") Solicitação de Nível
                  router-link(exact v-bind:to="{name: 'formsBook'}") Caderno IM / Projeto
              p.menu-label Consultar
              ul.menu-list
                li
                  router-link(exact v-bind:to="{name: 'formsTracker'}") Acompanhar Solicitação
          div.column.is-9.content-column
            transition(name="fade")
              router-view
    shortcuts
</template>

<script>
  import Breadcrumb from '../../components/breadcrumb/Breadcrumb.vue'
  import Shortcuts from '../../components/shortcuts/Shortcuts.vue'

  export default {
    components: {
      'shortcuts': Shortcuts,
      'breadcrumb': Breadcrumb
    },
    name: 'scout',
    data () {
      return {
        msg: ''
      }
    }
  }
</script>

<style scoped lang="sass">
  @import '~assets/sass/common.sass'
  // SCOUT BANNER
  .scout-banner
    background-blend-mode: multiply
    background-color: rgba(0, 0, 0, 0.3)
    background-image: url('~assets/images/forms-banner.jpg')
    background-size: cover
    background-repeat: no-repeat
    background-position: 0 60%
    .hero-body
      padding-top: 12rem
      min-height: 25rem
      section.container
        text-align: left
      .subtitle
        margin-bottom: 0px
        color: white
        text-transform: uppercase
        font-family: 'Roboto'
        font-weight: 300

  .scout-container
    background: rgba(233, 233, 233, 0.8)
    .main-container
      > .title
        text-transform: uppercase
      > .subtitle
        text-transform: lowercase
      padding-top: 2rem
      padding-bottom: 1rem
      .columns
        justify-content: space-between
</style>
