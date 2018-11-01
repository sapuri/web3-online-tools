<template>
  <div id="from-wei">
    <h3>fromWei</h3>
    <pre>web3.utils.fromWei(number [, unit])</pre>
    <p class="description">Converts any wei value into a ether value.</p>
    <div>
      <label for="number">number - String|Number|BN: The value in wei.</label><br>
      <input id="number" v-model="number" placeholder="number"><br><br>
      <label for="number">unit - String (optional, defaults to "ether"): The ether to convert to.</label><br>
      <input id="unit" v-model="unit" placeholder="unit (default: ether)">
      <br>
      <button v-on:click="run">Run</button>
      <p v-if="result" class="result">Result: {{ result }}</p>
      <p v-if="errorMsg" class="error-msg">{{ errorMsg }}</p>
    </div>
  </div>
</template>

<script>
  import * as web3 from "web3";

  export default {
    name: 'from-wei',
    data() {
      return {
        number: '',
        unit: '',
        result: '',
        errorMsg: ''
      }
    },
    methods: {
      run: function () {
        this.result = '';
        this.errorMsg = '';
        try {
          this.result = web3.utils.fromWei(this.number, this.unit).toString();
        } catch (e) {
          this.errorMsg = e.toString();
        }
      }
    }
  }
</script>

<style scoped>

</style>
