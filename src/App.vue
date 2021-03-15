<template>
  <div id="app">
    <Rating :star="2" :starSize="starSize" :hasResults="true" :hasDescription="true" :ratingDescription="desc" />
  </div>
</template>

<script>
import Rating from './components/Rating'

export default {
  name: 'app',
  components: {
    Rating
  },
  data() {
    return {
      desc: [
        {
          text: 'Poor',
          class: 'star-poor'
        },
        {
          text: 'Below Average',
          class: 'star-belowAverage'
        },
        {
          text: 'Average',
          class: 'star-average'
        },
        {
          text: 'Good',
          class: 'star-good'
        },
        {
          text: 'Excellent',
          class: 'star-excellent'
        }
      ],
      starSize: 'lg' //xs/6x
    }
  }
}
</script>
