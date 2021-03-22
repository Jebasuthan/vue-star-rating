<template>
  <div id="app">
    <AwesomeVueStarRating :star="this.star" :starsize="this.starsize" :hasresults="this.hasresults" :hasdescription="this.hasdescription" :ratingdescription="this.ratingdescription"/>
  </div>
</template>

<script>
import AwesomeVueStarRating from 'awesome-vue-star-rating'

export default {
  name: 'App',
  components: {
    AwesomeVueStarRating
  },
  data() {
    return {
      star: 5,
      ratingdescription: [
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
      hasresults: true,
      hasdescription: true,
      starsize: 'lg' //xs/6x
    }
  }
}
</script>
