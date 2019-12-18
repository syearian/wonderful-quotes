<template>
  <form class="add-quote-form">
    <div class="field">
      <label for="" class="label">Enter Quote Below</label>
      <div class="control">
        <textarea class="textarea" placeholder="Enter new quote here" v-model="newQuote"></textarea>
      </div>
    </div>
    <div class="field">
      <div class="control submit-control">
        <button class="button is-link" @click.prevent="addQuote">Add Quote</button>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      newQuote: ''
    }
  },
  methods: {
    addQuote() {
      this.$emit('addQuote', this.newQuote);
      this.newQuote = '';
    }
  }
}
</script>

<style>
.add-quote-form {
  margin: 0 auto;
  padding: 0 1.5rem;
  width: 80%;
}
.submit-control {
  text-align: center;
}
</style>