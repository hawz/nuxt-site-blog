<template>
  <div id="about-page" class="page-wrapper about-page content-page">
    <site-hero
      title="About me"
      subtitle=""
      image="/uploads/me-SRT-big.jpeg"
    ></site-hero>
    <main-section theme="sidebar-right">
      <template v-slot:default>
        <div class="content">
          <h3>Who am I 🤔</h3>
          <p>
            I am a front end web developer pushing code from Sassari, Italy. I
            have experience in creating interactive websites and multilingual
            applications in English and Italian for over 10 years. I not only
            design but hand code in a number of programming languages. Check out
            my
            <nuxt-link to="/portfolio">
              Portfolio
            </nuxt-link>
            and
            <a href="/vitae.pdf" target="_blank">
              CV
            </a>
            , then feel free to
            <nuxt-link to="/contact">
              reach out
            </nuxt-link>
            if you could use a hand.
          </p>
          <h3>Things I like 😋</h3>
          <p>
            I have a passion for beautiful code, making things work and front
            end development frameworks: I started with AngularJS back in 2014,
            then discovered Angular, and finally switched to (and fell in ❤️
            with) Vue.js and React. Plus, I have a passion for Rails, which I
            try to keep up with and I use for some side-project that probably
            will never see the light of day. I like tidiness in all its forms,
            probably due to a little OCD.
          </p>
          <p>
            I love cats, playing basketball, hiking, riding my motorbike and
            mountain bike, reading graphic novels and nordic noirs, eating any
            kind of food (everything but tripe, it's like Kryptonite to me 🤢),
            traveling to any kind of destination, especially the Nordics.
          </p>
          <h3>Sardinia 🏝</h3>
          <p>
            It's a wonderful island in the Mediterranean, famous for its
            excellent climate and high
            <a
              target="_blank"
              href="https://www.bluezones.com/exploration/sardinia-italy/"
            >
              life expectancy
            </a>
            .
          </p>
        </div>
      </template>

      <template v-slot:sidebar>
        <h3 class="subtitle is-4">
          Latest Posts
        </h3>
        <posts-grid :per-row="1" :number="2" />
      </template>
    </main-section>
  </div>
</template>
<script>
// import QuoteCard from '~/components/cards/QuoteCard'
export default {
  head() {
    return {
      title: `About | ${this.$siteConfig.siteName}`
    }
  }
  // components: { QuoteCard }
}
</script>
