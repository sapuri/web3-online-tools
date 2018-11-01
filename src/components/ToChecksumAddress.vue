<template>
  <div id="to-checksum-address">
    <h3>Convert to Checksum Address</h3>
    <p>web3.utils.toChecksumAddress([address])</p>
    <div>
      <input v-model="address" placeholder="0x...">
      <br>
      <button v-on:click="run">Run</button>
      <p v-if="checksumAddress" class="result">Checksum Address: {{ checksumAddress }}</p>
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
        checksumAddress: '',
        errorMsg: ''
      }
    },
    methods: {
      run: function () {
        this.checksumAddress = '';
        this.errorMsg = '';
        try {
          this.checksumAddress = web3.utils.toChecksumAddress(this.address);
        } catch (e) {
          this.errorMsg = e.toString();
        }
      }
    }
  }
</script>

<style scoped>

</style>
