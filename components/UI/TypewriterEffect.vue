<template>
  <span>
    I am
    <nuxt-link to="/about/">
      <span class="typed-text">{{ typeValue }}</span>
    </nuxt-link>
    <span class="cursor" :class="{ typing: typeStatus }">&nbsp;</span>
  </span>
</template>

<script>
export default {
  props: {
    typeArray: {
      type: Array,
      default: () => ['fun', 'awesome', 'strong', 'the walrus']
    }
  },
  data() {
    return {
      typeValue: '',
      typeStatus: false,
      typingSpeed: 150,
      erasingSpeed: 100,
      newTextDelay: 2000,
      typeArrayIndex: 0,
      charIndex: 0
    }
  },
  created() {
    setTimeout(this.typeText, this.newTextDelay + 200)
  },
  methods: {
    typeText() {
      if (this.charIndex < this.typeArray[this.typeArrayIndex].length) {
        if (!this.typeStatus) {
          this.typeStatus = true
        }
        this.typeValue += this.typeArray[this.typeArrayIndex].charAt(
          this.charIndex
        )
        this.charIndex += 1
        setTimeout(this.typeText, this.typingSpeed)
      } else {
        this.typeStatus = false
        setTimeout(this.eraseText, this.newTextDelay)
      }
    },
    eraseText() {
      if (this.charIndex > 0) {
        if (!this.typeStatus) {
          this.typeStatus = true
        }
        this.typeValue = this.typeArray[this.typeArrayIndex].substring(
          0,
          this.charIndex - 1
        )
        this.charIndex -= 1
        setTimeout(this.eraseText, this.erasingSpeed)
      } else {
        this.typeStatus = false
        this.typeArrayIndex += 1
        if (this.typeArrayIndex >= this.typeArray.length) {
          this.typeArrayIndex = 0
        }
        setTimeout(this.typeText, this.typingSpeed + 1000)
      }
    }
  }
}
</script>

<style>
span.typed-text {
  color: #00d1b2;
}

span.cursor {
  display: inline;
  margin: 3px;
  width: 4px;
  background-color: #ccc;
  animation: cursorBlink 1s infinite;
}

span.cursor.typing {
  animation: none;
}

@keyframes cursorBlink {
  49% {
    background-color: #ccc;
  }
  50% {
    background-color: transparent;
  }
  99% {
    background-color: transparent;
  }
}
</style>
