<script>
export default {
  name: 'RebelAds',

  data: function () {
    return {
      ads: {}
    }
  },

  watch: {
    '$route' (to, from) {
      if (
        to.path !== from.path
        // Only reload if the ad has been loaded
        // otherwise it's possible that the script is appended but
        // the ads are not loaded yet. This would result in duplicated ads.
        && this.$el.querySelector('#rebelads')
      ) {
        this.$el.innerHTML = ''
        this.load()
      }
    }
  },

  mounted () {
    this.load()
  },

  methods: {
    load () {
      const s = document.createElement('a')
      const i = document.createElement('img')
      s.href = 'https://www.google.com'
      i.src = '/images/green.png'
      i.className = 'img-responsive'
      s.appendChild(i);
      this.$el.appendChild(s)
    }
  },

  render (h) {
    return h('div', { class: 'rebel-ads' })
  }
}
</script>

<style lang="stylus">
.rebel-ads
  text-align: center
  vertical-align: text-top
  a
    color #444
    font-weight normal
    display inline
  img
    max-width 250px
    float left
    margin 1rem 1.5rem .5rem 1.5rem
    border 1px solid $borderColor
    display block

@media (max-width: $MQMobile)
  .rebel-ads
    img
      max-width 200px
</style>
