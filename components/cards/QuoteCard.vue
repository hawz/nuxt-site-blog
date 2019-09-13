<template>
  <div class="card quote-card">
    <div class="card-content">
      <p class="title">“{{ quote }}”</p>
      <p class="subtitle right">~ {{ author }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    quote: {
      type: String
    },
    author: {
      type: String
    }
  }
}
</script>
