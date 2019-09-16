<template>
  <div class="modal" :class="{ 'is-active': isActive }">
    <div class="modal-background" @click="closeModal"></div>
    <div v-if="project" class="modal-card">
      <header class="modal-card-head">
        <p class="modal-card-title">
          {{ project.title }}
        </p>
        <button class="delete" aria-label="close" @click="closeModal"></button>
      </header>
      <section class="modal-card-body">
        <figure v-if="project.image" class="image">
          <a :href="responsiveImage.src" target="_blank">
            <img :src="responsiveImage.src" />
          </a>
        </figure>
        <br />
        <p>
          {{ project.description }}
        </p>
      </section>
      <footer class="modal-card-foot">
        <button class="button" @click="closeModal">
          Cancel
        </button>
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isActive: {
      type: Boolean,
      default: false
    },
    closeModal: {
      type: Function,
      default: () => {}
    },
    project: {
      type: Object,
      default: null
    }
  },
  computed: {
    responsiveImage() {
      if (this.project.image.indexOf('/uploads') === 0) {
        return require(`~/assets${this.project.image}`)
      }
      return { src: this.image, srcSet: '' }
    }
  }
}
</script>
