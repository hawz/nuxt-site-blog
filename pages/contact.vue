<template>
  <div id="contact-page" class="page-wrapper contact-page content-page">
    <site-hero
      title="Contact Me"
      subtitle="Need some help? Get in touch!"
      image="/uploads/contact-hero.jpg"
    ></site-hero>
    <main-section theme="sidebar-right">
      <template v-slot:default>
        <div class="tile is-ancestor">
          <div class="tile is-parent">
            <article class="tile is-child box">
              <p class="title">
                Hello
              </p>
              <p class="subtitle">
                What can I do for you?
              </p>
              <figure class="image is-1by1">
                <opti-image
                  :src="require('~/assets/uploads/contact-burns.jpg').src"
                  :srcset="require('~/assets/uploads/contact-burns.jpg').srcSet"
                />
              </figure>
              <br />
              <div class="content">
                <p>
                  Feel free to reach me through the contact form or one of the
                  following options.
                </p>
                <p class="has-text-centered">
                  <a target="_blank" href="https://github.com/hawz">
                    <font-awesome-layers full-width class="fa-3x">
                      <font-awesome-icon :icon="['fab', 'github']" />
                    </font-awesome-layers>
                  </a>
                  <a target="_blank" href="https://twitter.com/devAlbe">
                    <font-awesome-layers full-width class="fa-3x">
                      <font-awesome-icon :icon="['fab', 'twitter']" />
                    </font-awesome-layers>
                  </a>
                  <a target="_blank" href="https://www.instagram.com/dev_albe">
                    <font-awesome-layers full-width class="fa-3x">
                      <font-awesome-icon :icon="['fab', 'instagram']" />
                    </font-awesome-layers>
                  </a>
                  <a
                    target="_blank"
                    href="https://stackoverflow.com/story/alberto.masia"
                  >
                    <font-awesome-layers full-width class="fa-3x">
                      <font-awesome-icon :icon="['fab', 'stack-overflow']" />
                    </font-awesome-layers>
                  </a>
                  <a
                    target="_blank"
                    href="https://www.linkedin.com/in/alberto-masia-b63b5b146"
                  >
                    <font-awesome-layers full-width class="fa-3x">
                      <font-awesome-icon :icon="['fab', 'linkedin']" />
                    </font-awesome-layers>
                  </a>
                </p>
              </div>
            </article>
          </div>
          <div class="tile is-parent is-8">
            <article class="tile is-child box">
              <contact-form />
            </article>
          </div>
        </div>
      </template>
      <template v-slot:sidebar>
        <h3 class="subtitle is-4">
          Latest Posts
        </h3>
        <!-- Latest Posts -->
        <posts-grid :per-row="1" :number="2" />
      </template>
    </main-section>
  </div>
</template>
<script>
import ContactForm from '~/components/ContactForm'
export default {
  head() {
    return {
      title: `Contact | ${this.$siteConfig.siteName}`
    }
  },
  components: { ContactForm }
}
</script>
