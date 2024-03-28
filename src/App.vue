<template lang="">
  <div>
    <Header></Header>
    <Container>
      <ApartmentFilterForm @submit="logger" />
    </Container>
    <ApartmentsList :items="apartments" />
  </div>
</template>
<script>
import Header from "./components/Header.vue";
import ApartmentsList from "./components/apartment/ApartmentsList.vue";
import apartments from "./components/apartment/apartments";
import ApartmentFilterForm from "./components/apartment/ApartmentFilterForm.vue";
import Container from "./components/shared/Container.vue";
export default {
  data() {
    return {
      context: "jvv",
      apartments,
    };
  },
  components: {
    Header,
    ApartmentsList,
    Container,
    ApartmentFilterForm,
  },
  methods: {
    logger: function (value) {
      console.log(value);
    },
  },
};
</script>
<style lang="scss"></style>
