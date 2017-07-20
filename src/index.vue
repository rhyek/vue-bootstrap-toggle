<template>
   <input type="checkbox"/>
</template>

<script>
import merge from 'merge'

export const defaults = {}

if (!jQuery().bootstrapToggle) {
  require('bootstrap-toggle')
}

export default {
  props: {
    value: Boolean,
    options: {
      type: Object,
      default: () => ({})
    }
  },
  computed: {
    $$el() {
      return jQuery(this.$el)
    }
  },
  watch: {
    value(newValue) {
      this.$$el.bootstrapToggle(newValue ? 'on' : 'off')
    }
  },
  mounted() {
    if (this.value) {
      this.$el.checked = true
    }
    this.$$el.bootstrapToggle(merge.recursive(true, defaults, this.options))
    this.$$el.change(() => {
      this.$emit('input', this.$$el.prop('checked'))
    })
  },
  beforeDestroy() {
    this.$$el.bootstrapToggle('destroy')
    this.$$el.off('change')
  }
}
</script>

<style src="bootstrap-toggle/css/bootstrap-toggle.css"/>