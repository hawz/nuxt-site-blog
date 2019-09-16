<template>
  <div id="about-page" class="page-wrapper about-page content-page">
    <site-hero
      title="Portfolio"
      subtitle="Some of the most relevant projects I've been involved in."
      image="https://picsum.photos/1800/1801"
    ></site-hero>
    <main-section theme="one-column">
      <template v-slot:default>
        <div class="content">
          <p>
            Check out my
            <a target="_blank" href="https://github.com/hawz">Github</a> profile
            for more side projects I've worked on in my spare time, or to keep
            up with some interesting technology.
          </p>
        </div>
        <div class="tile is-ancestor">
          <div class="tile is-8 is-parent">
            <article class="tile is-child box" @click="openModal(portfolio[0])">
              <p class="title">
                {{ portfolio[0].title }}
              </p>
              <p class="subtitle">
                {{ portfolio[0].subtitle }}
              </p>
              <p>
                <small class="has-text-grey">
                  {{ portfolio[0].client }}
                </small>
                <small class="has-text-grey is-pulled-right">
                  {{ portfolio[0].tech }}
                </small>
              </p>
            </article>
          </div>
          <div class="tile is-parent">
            <article class="tile is-child box" @click="openModal(portfolio[1])">
              <p class="title">
                {{ portfolio[1].title }}
              </p>
              <p class="subtitle">
                {{ portfolio[1].subtitle }}
              </p>
              <p>
                <small class="has-text-grey">
                  {{ portfolio[1].client }}
                </small>
                <small class="has-text-grey is-pulled-right">
                  {{ portfolio[1].tech }}
                </small>
              </p>
            </article>
          </div>
        </div>
        <div class="tile is-ancestor">
          <div class="tile is-parent">
            <article class="tile is-child box" @click="openModal(portfolio[2])">
              <p class="title">
                {{ portfolio[2].title }}
              </p>
              <p class="subtitle">
                {{ portfolio[2].subtitle }}
              </p>
              <p>
                <small class="has-text-grey">
                  {{ portfolio[2].client }}
                </small>
                <small class="has-text-grey is-pulled-right">
                  {{ portfolio[2].tech }}
                </small>
              </p>
            </article>
          </div>
          <div class="tile is-parent">
            <article class="tile is-child box" @click="openModal(portfolio[3])">
              <p class="title">
                {{ portfolio[3].title }}
              </p>
              <p class="subtitle">
                {{ portfolio[3].subtitle }}
              </p>
              <p>
                <small class="has-text-grey">
                  {{ portfolio[3].client }}
                </small>
                <small class="has-text-grey is-pulled-right">
                  {{ portfolio[3].tech }}
                </small>
              </p>
            </article>
          </div>
          <div class="tile is-parent">
            <article class="tile is-child box" @click="openModal(portfolio[4])">
              <p class="title">
                {{ portfolio[4].title }}
              </p>
              <p class="subtitle">
                {{ portfolio[4].subtitle }}
              </p>
              <p>
                <small class="has-text-grey">
                  {{ portfolio[4].client }}
                </small>
                <small class="has-text-grey is-pulled-right">
                  {{ portfolio[4].tech }}
                </small>
              </p>
            </article>
          </div>
        </div>
        <div class="tile is-ancestor">
          <div class="tile is-parent">
            <article class="tile is-child box" @click="openModal(portfolio[5])">
              <p class="title">
                {{ portfolio[5].title }}
              </p>
              <p class="subtitle">
                {{ portfolio[5].subtitle }}
              </p>
              <p>
                <small class="has-text-grey">
                  {{ portfolio[5].client }}
                </small>
                <small class="has-text-grey is-pulled-right">
                  {{ portfolio[5].tech }}
                </small>
              </p>
            </article>
          </div>
          <div class="tile is-8 is-parent">
            <article class="tile is-child box" @click="openModal(portfolio[6])">
              <p class="title">
                {{ portfolio[6].title }}
              </p>
              <p class="subtitle">
                {{ portfolio[6].subtitle }}
              </p>
              <p>
                <small class="has-text-grey">
                  {{ portfolio[6].client }}
                </small>
                <small class="has-text-grey is-pulled-right">
                  {{ portfolio[6].tech }}
                </small>
              </p>
            </article>
          </div>
        </div>
        <div class="tile is-ancestor">
          <div class="tile is-parent">
            <article class="tile is-child box" @click="openModal(portfolio[7])">
              <p class="title">
                {{ portfolio[7].title }}
              </p>
              <p class="subtitle">
                {{ portfolio[7].subtitle }}
              </p>
              <p>
                <small class="has-text-grey">
                  {{ portfolio[7].client }}
                </small>
                <small class="has-text-grey is-pulled-right">
                  {{ portfolio[7].tech }}
                </small>
              </p>
            </article>
          </div>
          <div class="tile is-parent">
            <article class="tile is-child box" @click="openModal(portfolio[8])">
              <p class="title">
                {{ portfolio[8].title }}
              </p>
              <p class="subtitle">
                {{ portfolio[8].subtitle }}
              </p>
              <p>
                <small class="has-text-grey">
                  {{ portfolio[8].client }}
                </small>
                <small class="has-text-grey is-pulled-right">
                  {{ portfolio[8].tech }}
                </small>
              </p>
            </article>
          </div>
          <div class="tile is-parent">
            <article class="tile is-child box" @click="openModal(portfolio[9])">
              <p class="title">
                {{ portfolio[9].title }}
              </p>
              <p class="subtitle">
                {{ portfolio[9].subtitle }}
              </p>
              <p>
                <small class="has-text-grey">
                  {{ portfolio[9].client }}
                </small>
                <small class="has-text-grey is-pulled-right">
                  {{ portfolio[9].tech }}
                </small>
              </p>
            </article>
          </div>
        </div>
      </template>

      <template v-slot:sidebar>
        Nothing here
      </template>
    </main-section>
    <Modal
      :is-active="isActive"
      :close-modal="closeModal"
      :project="selectedProject"
    />
  </div>
</template>
<script>
import Modal from '~/components/UI/Modal'
export default {
  head() {
    return {
      title: `Portfolio | ${this.$siteConfig.siteName}`
    }
  },
  components: { Modal },
  data() {
    return {
      isActive: false,
      selectedProject: null,
      portfolio: [
        {
          title: 'Inpeco',
          subtitle: 'UI for Clinical Lab Automation',
          description: `
            I worked on creating from scratch ten different AngularJS SPAs
            for the medical industry automation leader Inpeco SA, each application
            connected (using the MQTT protocol) to complex medical devices.
            I was also involved in writing unit testing with Jasmine and API design activity.
          `,
          thumbImage: '',
          image: '/uploads/portfolio/inpeco-logo.png',
          client: 'Inpeco SA',
          url: 'https://www.inpeco.com/en/',
          tech: 'AngularJS - HTML - CSS'
        },
        {
          title: 'Snai.it',
          subtitle: 'Live Sports Betting Odds',
          description: `
            SNAI is one of the major Italian sports
            betting companies. For them, I worked on three main sections
            of the website which are the Live, Virtuali and Ippica
            modules, each one receiving real-time updates about results,
            new events and betting odds via web socket. Each section is
            also connected to the shopping cartm which updates odds and
            total amount in real-time.
          `,
          thumbImage: '',
          image: '/uploads/portfolio/snai-live-section.jpg',
          client: 'SNAI Spa',
          url: 'https://www.snai.it',
          tech: 'AngularJS - HTML - CSS'
        },
        {
          title: 'TOL',
          subtitle: 'Online Placement Testing tool for English School Websites',
          description: `
            In this project, I created a Vue.js application within the English School
website, to allow students coming for the first time to the school to take the placement test with a user interface easier than the excel sheets used so far.
I enjoyed using Vue and Vuex for state management.
          `,
          thumbImage: '',
          image: '/uploads/portfolio/tol.jpg',
          client: 'The English Centre',
          url: 'https://www.theenglishcentreonline.com',
          tech: 'Vue.js - Vuex - Laravel'
        },
        {
          title: 'BG Lab',
          subtitle: 'E-Learning Platform',
          description: `
            I worked on an AngularJS application for the internal e-learning solution used
            by the employees of Banca Generali. I focused on the user interface, the credits
            assignment and the certificate release mechanism.
          `,
          thumbImage: '',
          image: '/uploads/portfolio/bg-lab.png',
          client: 'Banca Generali',
          url: '',
          tech: 'AngularJS - HTML - CSS'
        },
        {
          title: 'oFootball',
          subtitle: 'Online Soccer Manager Game',
          description: `
            oFootball is a Soccer Manager Game. On their website, or through
            the Facebook app, you can register and create your team, subscribe
            to different leagues and manage every detail of your kickers,
            such as training, auctions, strategy, etc.
          `,
          thumbImage: '',
          image: '/uploads/portfolio/ofootball.jpg',
          client: 'Bangbite Srl',
          url: '',
          tech: 'Rails - Jade - CoffeeScript'
        },
        {
          title: 'League of Dodgers',
          subtitle: 'Online Soccer Manager Game',
          description: `
            League of Dodgers is an AngularJS project I've been involved in for 10 months.
            Starting from the oFootball experience, we didn't start building the typical
            soccer manager game, but something where you could cheat, buying matches,
            beating kickers, etc.
          `,
          thumbImage: '',
          image: '/uploads/portfolio/dirtySoccer.jpg',
          client: 'Bangbite Srl',
          url: '',
          tech: 'AngularJS - HTML - CSS'
        },
        {
          title: 'Color LAB',
          subtitle: 'Online Contest - SVG Configurator',
          description: `
            ColorLAB is a contest hosted by Donnamoderna from May 18th to July 12th 2015.
            You are challenged to test your creativity, selecting an uncolored room in the
            house and filling it with colors. Each approved creation is shown inside the
            gallery and can win the final prize.
          `,
          thumbImage: '',
          image: '/uploads/portfolio/coloreria_1.jpg',
          client: 'Kiver Srl',
          url: '',
          tech: 'CodeIgniter - jQuery - SVG'
        },
        {
          title: 'FlowPop',
          subtitle: 'User Research Tool',
          description: `
            Flowpop is an independent project for a user research tool I've been
            involved in since October 2014, together with two friends, a backend
            developer and a UX Designer. On one side, it solves the problem for
            startups, website and e-commerce owners, of gathering knowledge about
            their users, thus being able to show them proper offers and feedback
            requests. On the other, it avoids obnoxious popups to uninterested users,
            thus increasing their surfing experience and improving those metrics the
            owners care about, like bounce rate, conversion rate, cart abandonment, etc.
          `,
          thumbImage: '/uploads/portfolio/flowpopLogo.jpg',
          image: '/uploads/portfolio/flowpopPage.jpg',
          client: '',
          url: '',
          tech: 'JavaScript'
        },
        {
          title: 'Wasabi Peas',
          subtitle: 'Information Technology Professionals',
          description: `
            Wasabi Peas is a network of independent Information Technology
            professionals with hard skills in all the fields needed to accomplish
            complex projects for web and mobile applications development and system
            integration. Our customers are some of the major Italian and international
            players in web marketing, gaming and entertainment, as well as small and
            medium companies looking for effective IT solutions at a better price.
          `,
          thumbImage: '/uploads/portfolio/wasabiLogo.jpg',
          image: '/uploads/portfolio/wasabiPage.jpg',
          client: '',
          url: '',
          tech: 'Web Development'
        },
        {
          title: 'Sounday Music',
          subtitle: 'Digital Music Ecosystem',
          description: `
            Sounday is an online music label, a Digital Music Ecosystem and a web-mobile
            platform offering advanced solutions and services to people active in the
            music world. I was involved as fullstack PHP engineer in the development of
            the first version of the platform from 2011 to the end of 2012.
          `,
          thumbImage: '/uploads/portfolio/soundayLogo.jpg',
          image: '/uploads/portfolio/soundayPage.jpg',
          client: 'Sounday Srl',
          url: '',
          tech: 'JavaScript - PHP'
        }
      ]
    }
  },
  methods: {
    openModal(project) {
      this.isActive = true
      this.selectedProject = project
    },
    closeModal() {
      this.isActive = false
      this.selectedProject = null
    }
  }
}
</script>

<style scoped>
article {
  cursor: pointer;
}
</style>
