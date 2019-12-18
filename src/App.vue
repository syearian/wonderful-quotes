<template>
  <div id="app" class="container">
    <ProgressBar :progress="progress"></ProgressBar>
    <AddQuote @addQuote="addNewQuote"></AddQuote>
    <section class="section quote-list">
      <SingleQuote v-for="(item, index) in quoteList" :key="item.id" @removeQuote="removeQuote(index)">
        <p><em>{{ item.quote }}</em></p>
      </SingleQuote>
    </section>
    <footer class="notification is-info">
      <p class="has-text-centered">Info: Click on a quote to delete it.</p>
    </footer>
  </div>
</template>

<script>
import ProgressBar from './components/ProgressBar';
import AddQuote from './components/AddQuote';
import SingleQuote from './components/SingleQuote';

export default {
  name: 'app',
  components: {
    ProgressBar,
    AddQuote,
    SingleQuote
  },
  data() {
    return {
      quoteList: [
        {
          id: 0,
          quote: 'This is the original quote!'
        }
      ],
      newId: 1,
      progress: 1
    }
  },
  methods: {
    addNewQuote(newQuote) {
      if (this.progress < 10) {
        this.progress++;
        this.quoteList.push({
          id: this.newId,
          quote: newQuote
          });
        this.newId++;
      } else {
        alert('Quote limit has been reached.')
      }
    },
    removeQuote(index) {
      this.quoteList.splice(index, 1);
      this.progress--;
    }
  }
}
</script>

<style lang="scss">
.quote-list {
  display: flex;
  justify-content: center;
  align-items: stretch;
  flex-wrap: wrap;
}
</style>
