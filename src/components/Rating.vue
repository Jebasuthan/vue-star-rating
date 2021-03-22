<template>
  <div class="rating">
    <ul class="list">
      <li :key="star" v-for="star in maxstars" @mouseover="hoverStar(star)"
    @mouseleave="mouseLeftStar" :class="{ 'active': star <= stars }" @click="rate(star)" class="star">
        <font-awesome-icon :size="starSize" :icon="[star <= stars ? 'fas' : 'far', 'star']"/>
      </li>
      <span v-if="hasdescription" :class="star_desc.class">{{star_desc.text}}</span>
    </ul>
    <span v-if="hasresults">{{ stars }} of {{ maxstars }}</span>
  </div>
</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core'
import { fas } from '@fortawesome/free-solid-svg-icons'
import { far } from '@fortawesome/free-regular-svg-icons'
library.add(fas)
library.add(far)
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

export default {
  name: 'vue_star_rating',
  components: {
    FontAwesomeIcon
  },
  data() {
    return {
      stars: this.star,
      star_desc: this.getRatingDesc(this.star)
    }
  },
  props:{
    star: {
      type: Number
    },
    maxstars: {
      type: Number,
      default: 5
    },
    hasresults: {
      type: Boolean,
      default: true
    },
    hasdescription: {
      type: Boolean,
      default: true
    },
    ratingdescription: {
      type: Array,
      default: () => {
        return [{
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
        }]
      }
      //default: ["Poor", "Below Average", "Average", "Good", "Excellent"]
    },
    starsize: {
      type: String,
      default: 'lg'
    }
  },
  methods: {
    rate(star) {
      if (star <= this.maxstars && star >= 0) {
        this.stars = this.stars === star ? star - 1 : star
      }
    },
    hoverStar(star) {
      if (star <= this.maxstars && star >= 0) {
        this.star_desc = this.ratingdescription[star - 1]
      }
    },
    mouseLeftStar() {
      if(this.stars) {
        this.star_desc = this.ratingdescription[this.stars - 1]
        return this.star_desc
      } else {
        this.star_desc = ''
      }
    },
    getRatingDesc(star) {
      if(star) {
        this.star_desc = this.ratingdescription[star - 1]
      }
      return this.star_desc
    }
  }
}
</script>

<style scoped lang="scss">
  $active-color: #f3d23e;
  $white-color: #fff;
  $poor-color: rgb(186, 186, 186);
  $below-average-color: rgb(245, 195, 87);
  $average-color: rgb(255, 172, 90);
  $good-color: rgb(193, 215, 89);
  $excellent-color: rgb(72, 150, 77);
  .rating {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
  ul.list li, span {
    display: inline-block;
    margin: 2px;
  }
  .list {
    margin: 0 0 5px 0;
    padding: 0;
    list-style-type: none;
    &:hover {
      .star {
        color: $active-color;
      }
    }
    span {
      width: 130px;
      margin-left: 5px;
      padding: 2px;
      color: $white-color;
      border-radius: 2px;
      font-size: 13px;
      text-align: center;
      font-weight: bold;
      transition: .2s;
      line-height: 25px;
    }
  }
  .star {
    cursor: pointer;
    &:hover {
      &~.star {
        &:not(.active) {
          color: inherit;
        }
      }
    }
  }
  .active {
    color: $active-color;
  }
  .star-poor {
    background: $poor-color;
  }
  .star-belowAverage {
    background: $below-average-color;
  }
  .star-average {
    background: $active-color;
  }
  .star-good {
    background: $good-color;
  }
  .star-excellent {
    background: $excellent-color;
  }
</style>
