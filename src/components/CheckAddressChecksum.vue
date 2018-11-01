<template>
  <div id="check-address-checksum">
    <h3>checkAddressChecksum</h3>
    <pre>web3.utils.checkAddressChecksum(address)</pre>
    <p class="description">Checks the checksum of a given address. Will also return false on non-checksum addresses.</p>
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
    name: 'check-address-checksum',
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
          this.result = web3.utils.checkAddressChecksum(this.address).toString();
        } catch (e) {
          this.errorMsg = e.toString();
        }
      }
    }
  }
</script>

<style scoped>

</style>
