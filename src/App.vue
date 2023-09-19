<template>
  <div class="bmi">
    <div class="bmi__hero">
      <h1>BMI</h1>
      <P> calculator </P>
    </div>
    <PageView />
  </div>
</template>

<script>
import PageView from "./components/PageView.vue";
export default {
  components: { PageView },
};
</script>

<style>
body {
  background: white;
}
</style>
