<template lang="">
  <div class="star_rating">
    <span
      v-for="index in starLimit"
      :key="index"
      class="star star--outlined"
    ></span>
    <div class="star_rating__fullfilled" :style="`width:${ratingWidth};`">
      <span
        v-for="index in starLimit"
        :key="index"
        class="star star--colored"
      ></span>
    </div>
  </div>
</template>
<script>
export default {
  name: "StarRating",
  props: {
    rating: {
      type: Number,
      default: 0,
    },
    starLimit: {
      type: Number,
      default: 5,
    },
  },
  computed: {
    ratingWidth() {
      return (this.rating / this.starLimit) * 100 + "%";
    },
  },
};
</script>
<style lang="scss">
.star_rating {
  position: relative;
  display: inline-flex;
  &__fullfilled {
    display: inline-flex;
    position: absolute;
    width: 0;
    height: 100%;
    top: 0;
    left: 0;
    overflow: hidden;
  }
}

.star {
  display: inline-block;
  width: 16px;
  height: 16px;
  margin: 0 3px;
  flex-shrink: 0;
  &--colored {
    background: url("/img/star_yellow.svg") center no-repeat;
  }
  &--outlined {
    background: url("/img/star_outline.svg") center no-repeat;
  }
}
</style>
