<template>
  <div class="form">
    <div class="form__img">
      <img src="../img/1.jpg" alt="boy" />
    </div>
    <div class="form__box">
      <div class="form__box__inputs">
        <input type="text" placeholder="type your Height..." ref="height" />
        <input type="text" placeholder="type your Weight..." ref="weight" />
      </div>
      <button @click="calculate"> Calculate... </button>
      <p>{{ text }}</p>
    </div>

    <div class="form__img">
      <img src="../img/2.jpg" alt="girl" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: " ",
    };
  },
  methods: {
    calculate() {
      const height = this.$refs.height.value;
      const weight = this.$refs.weight.value;
      const bmi = Math.round(weight / ((height * height) / 10000).toFixed(2));

      if (height == "" || weight == "") {
        this.text = "Please enter a valid value...!!";
      } 
      else if(bmi<11){
        this.text = "you're dead...!  :)";
      }
      else if (bmi>11 && bmi < 18.6) {
        this.text = "Under weight : " + bmi;
      } else if (bmi >= 18.6 && bmi < 24.9) {
        this.text = "Normal weight : " + bmi;
      } else {
        this.text = "Over weight : " + bmi;
      }
    },
  },
};
</script>

<style scoped>
</style>