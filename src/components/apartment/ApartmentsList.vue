<template lang="">
  <Container>
    <div class="apartments-list">
      <ApartmentItem
        v-for="item in items"
        :key="item.id"
        :descr="item.descr"
        :rating="item.rating"
        :price="item.price"
        :imgSrc="item.imgUrl"
      />
    </div>
  </Container>
</template>
<script>
import ApartmentItem from "./ApartmentItem.vue";
import Container from "../shared/Container.vue";

export default {
  name: "ApartmentsList",
  components: {
    ApartmentItem,
    Container,
  },
  props: {
    items: {
      type: Array,
      default: () => [],
    },
  },
};
</script>
<style lang="scss" scoped>
.apartments-list {
  display: flex;
  flex-wrap: wrap;
  margin-left: -15px;
  margin-right: -15px;
}
</style>
