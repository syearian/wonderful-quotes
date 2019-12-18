<template>
  <section class="section">
    <h2 class="is-size-3">Quotes Added</h2>
    <div class="progress-wrapper">
      <div class="progress-bar has-background-link" :style="[ progressBarWidth ]">
        <span>{{ progress }}/10</span>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: ['progress'],
  computed: {
    progressBarWidth() {
      return {
        width: this.progress + '0%'
      }
    }
  }
}
</script>

<style>
.progress-wrapper {
  width: 100%;
  border-radius: 1rem;
  background-color: #eee;
  transition: width 500ms;
}
.progress-bar {
  padding: .25rem 1rem;
  width: 10%;
  border-radius: 1rem;
  text-align: center;
  color: white;
}
</style>