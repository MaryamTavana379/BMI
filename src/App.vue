

<template>
  <div class="inputs">
    <input
      type="text"
      placeholder="type your Height"
      ref="height"
    />
    <input
      type="text"
      placeholder="type your Weight"
      ref="weight"
    />
    <button @click="calculate">محاسبه</button>
    <p>{{ text }}</p>
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
      const height = this.$refs.height.value
      const weight = this.$refs.weight.value
      const bmi = Math.round( weight / ((height * height) / 10000).toFixed(2))
   
      
     
      if(height == "" || weight == ""){
        this.text = "Please enter a valid value...!!"
      }
      else if(bmi < 18.6) {
        this.text = "Under weight : " + bmi
      }
      else if(bmi >= 18.6 && bmi < 24.9 ) {
        this.text = "Normal weight : " + bmi

      }
      else {
        this.text = "Over weight : " + bmi
      }

    },
  },
};
</script>

<style scoped>
.inputs {
  display: flex;
  flex-direction: column;
}
</style>
