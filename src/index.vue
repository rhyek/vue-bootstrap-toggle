<template>
   <input type="checkbox"/>
</template>

<script>
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
    mounted() {
      if (this.value) {
        this.$el.checked = true
      }
      this.$$el.bootstrapToggle(this.options)
      this.$$el.change(() => {
        this.$emit('input', !this.value)
      })
    },
    beforeDestroy() {
      this.$$el.bootstrapToggle('destroy')
      this.$$el.off('change')
    }
  }
</script>