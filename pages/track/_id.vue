<template lang="pug">
  .container(v-if="track && track.id")
    .columns
      .column.is-3.has-text-centered
        figure.media-left
          p.image
            img(:src="track.album.images[0].url")
      .column.is-8
        .panel
          .panel-heading
            h1.title {{ track.name }} - {{ track.artists[0].name }}
          .panel-block
            article.media
              .media-content
                .content
                  ul(v-for="(v, k) in track")
                    li
                      strong {{ k }}:&nbsp;
                      span {{ v }}
</template>

<script>
import trackService from '~/plugins/track'

export default {
  data() {
    return {
      track: {}
    }
  },
  head() {
    // Por medio del Hook head, se puede configurar cosas en cada página o
    // componentes como el head, el title, meta, links, etc.
    return {
      title: this.track.name
    }
  },
  asyncData({ params }) {
    const id = params.id
    return trackService.getById(id).then(res => {
      return { track: res }
    })
  }
}
</script>

<style lang="scss" scoped>
.columns {
  margin: 20px;
}
.button-bar {
  margin-top: 20px;
}
</style>
