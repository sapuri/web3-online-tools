<template>
  <div id="is-address">
    <h3>isAddress</h3>
    <pre>web3.utils.isAddress(address)</pre>
    <p>Checks if a given string is a valid Ethereum address. It will also check the checksum, if the address has upper
      and lowercase letters.</p>
    <div>
      <input v-model="address" placeholder="address">
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
    name: 'is-address',
    data() {
      return {
        address: '',
        result: '',
        errorMsg: ''
      }
    },
    methods: {
      run: function () {
        this.result = '';
        this.errorMsg = '';
        try {
          this.result = web3.utils.isAddress(this.address).toString();
        } catch (e) {
          this.errorMsg = e.toString();
        }
      }
    }
  }
</script>

<style scoped>

</style>
