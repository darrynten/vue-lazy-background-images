<template>
  <div>
    <div :class="imageState" :style="computedStyle" :data-width="imageWidth" :data-height="imageHeight" :data-state="imageState"></div>
  </div>
</template>

<script>
export default {
  props: {
    imageSource: {
      type: String,
      required: true
    },
    loadingImage: {
      type: String,
      required: true
    },
    errorImage: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      imageWidth: 0,
      imageHeight: 0,
      imageState: null,
      asyncImage: new Image()
    }
  },
  computed: {
    computedStyle() {
      
    }
  },
  methods: {
    fetchImage() {
      this.asyncImage.onload = this.imageOnLoad()
      this.asyncImage.onerror = this.imageOnError()
      this.imageState = 'loading'
      this.asyncImage.src = this.imageSource
    },
    imageOnLoad() {
      console.log(this, this.asyncImage, '===== SUCCESS ====')
      this.imageState = 'loaded'
      this.imageWith = this.asyncImage.naturalWidth
      this.imageHeight = this.asyncImage.naturalHeight
    },
    imageOnError() {
      console.log(this, this.asyncImage, '<<<< ERROR >>>>')
      this.imageState = 'error'
    }
  },
  mounted() {
    console.log('mounted')
  }
}
</script>
