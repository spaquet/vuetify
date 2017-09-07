<script>
  export default {
    name: 'v-avatar',

    functional: true,

    props: {
      size: {
        type: String,
        default: '48px'
      },
      tile: Boolean,
      border-style: {
        type: String,
        default: 'solid'
      },
      border-width: {
        type: String,
        default: '3px'
      },
      border-color: {
        type: String
        default: '#6a1b9a'
      }
    },

    render (h, { data, props, children }) {
      data.staticClass = (`avatar ${data.staticClass || ''}`).trim()
      data.style = data.style || {}

      if (props.tile) data.staticClass += ' avatar--tile'
      if (props.border) data.staticClass += ' avatar--solid-border'
      
      data.style.height = props.size
      data.style.width = props.size
      data.styke.border-style: props.border-style
      data.style.border-width: props.border-width
      data.style.border-color: props.border-color

      return h('div', data, children)
    }
  }
</script>

<style lang="stylus" src="../../stylus/components/_avatars.styl"></style>
