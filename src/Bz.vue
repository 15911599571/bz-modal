<template>
  <div class="ui small test modal transition hidden">
    <i v-show="show_close" class="close icon"></i>
    <slot></slot>
  </div>
</template>

<script>
  import $ from 'jquery'
  import transition from 'semantic-ui-transition'
  $.fn.transition = transition
  import dimmer from 'semantic-ui-dimmer'
  $.fn.dimmer = dimmer
  import modal from 'semantic-ui-modal'
  $.fn.modal = modal

  export default {
    props: {
      show_close: {
        default: false
      }
    },
    ready () {
      this.$on('modal', this.showModal)
    },
    methods: {
      showModal: function () {
        $(this.$el).modal('show')
      }
    }
  }
</script>
