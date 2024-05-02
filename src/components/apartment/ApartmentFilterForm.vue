<template>
  <form @click.prevent="handleSubmit" class="form">
    <CustomSelect v-model="city" :items="cities" class="select" />
    <CustomInput placeholder="Price, from" v-model="price" class="input" />
    <SubmitButton type="submit" class="btn">Find</SubmitButton>
  </form>
</template>
<script>
import CustomInput from "../shared/CustomInput.vue";
import CustomSelect from "../shared/CustomSelect.vue";
import SubmitButton from "../Button.vue";

export default {
  components: {
    CustomInput,
    CustomSelect,
    SubmitButton,
  },
  data() {
    return {
      price: "",
      city: "",
    };
  },

  computed: {
    cities() {
      return [
        { label: "City", value: "", selected: true },
        "Odesa",
        "Dnipro",
        "Poltava",
        "Kharkiv",
        "Mariupol",
        "Kyiv",
        "Kherson",
        "Lviv",
      ];
    },
  },

  methods: {
    handleSubmit() {
      return this.$emit("submit", { city: this.city, price: this.price });
    },
  },
};
</script>
<style lang="scss">
.form {
  display: flex;
  margin-block: 20px;
}

.input {
  margin-left: 20px;
}

.btn {
  text-align: center;
  margin-left: auto;
  padding: 8px 15px;
  width: 200px;
}
</style>
