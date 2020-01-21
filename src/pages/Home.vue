<template>
  <div class="wrapper-content wrapper-content--fixed">
    <section>
      <div class="container">
        <h1>Home page</h1>
      </div>
      <p>{{getMessage}}</p>
    </section>
  </div>
</template>

<script>
export default {
  computed: {
    getMessage() {
      return this.$store.getters.getMessage;
    }
  }
};
</script>