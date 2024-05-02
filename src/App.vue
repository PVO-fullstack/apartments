<template>
  <slot>
    <Header></Header>
    <Container>
      <ApartmentFilterForm @submit="filter" />
      <p v-if="filtredApartments.length === 0">No apartments</p>
      <ApartmentsList :items="filtredApartments" />
    </Container>
    <Footer></Footer>
  </slot>
</template>
<script>
import Header from "./components/Header.vue";
import ApartmentsList from "./components/apartment/ApartmentsList.vue";
import apartments from "./components/apartment/apartments";
import ApartmentFilterForm from "./components/apartment/ApartmentFilterForm.vue";
import Container from "./components/shared/Container.vue";
import Footer from "./components/Footer.vue";
export default {
  data() {
    return {
      apartments,
      filters: {
        city: "",
        price: 0,
      },
    };
  },
  computed: {
    filtredApartments() {
      return this.filterByCityName(this.filterByPrice(this.apartments));
    },
  },
  components: {
    Header,
    ApartmentsList,
    Container,
    ApartmentFilterForm,
    Footer,
  },
  methods: {
    filter({ city, price }) {
      console.log(city);
      this.filters.city = city;
      this.filters.price = price;
    },
    filterByCityName(apartments) {
      if (!this.filters.city) return apartments;

      return apartments.filter(
        (apartment) => apartment.location.city === this.filters.city
      );
    },
    filterByPrice(apartments) {
      if (!this.filters.price) return apartments;

      return apartments.filter(
        (apartment) => apartment.price >= this.filters.price
      );
    },
  },
};
</script>
<style lang="scss"></style>
