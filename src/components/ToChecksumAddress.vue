<template>
  <div id="to-checksum-address">
    <h3>toChecksumAddress</h3>
    <pre>web3.utils.toChecksumAddress(address)</pre>
    <p class="description">Will convert an upper or lowercase Ethereum address to a checksum address.</p>
    <div>
      <label for="address">address - String: An address string.</label><br>
      <input id="address" v-model="address" placeholder="address">
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
    name: 'to-checksum-address',
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
          this.result = web3.utils.toChecksumAddress(this.address);
        } catch (e) {
          this.errorMsg = e.toString();
        }
      }
    }
  }
</script>

<style scoped>

</style>
