<template>
  <div class="home">
    <h1>Web3 Online Tools</h1>
    <p>
      Online web3 tools using
      <a href="https://web3js.readthedocs.io/en/1.0/index.html" target="_blank" rel="noopener">web3.js</a>
      for support your dapps development
    </p>
    <p><a href="https://github.com/sapuri/web3-online-tools" target="_blank" rel="noopener">GitHub repository</a></p>
    <h3>Convert to Checksum Address</h3>
    <p>web3.utils.toChecksumAddress([address])</p>
    <div>
      <input v-model="address" placeholder="0x...">
      <br>
      <button v-on:click="convert">Convert</button>
      <p v-if="checksumAddress" class="result">Checksum Address: {{ checksumAddress }}</p>
      <p v-if="errorMsg" class="error-msg">{{ errorMsg }}</p>
    </div>
  </div>
</template>

<script>
  import * as web3 from "web3";

  export default {
    name: 'Home',
    data() {
      return {
        address: '',
        checksumAddress: '',
        errorMsg: ''
      }
    },
    methods: {
      convert: function () {
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h3 {
    margin: 40px 0 0;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }

  .result {
    color: green;
  }

  .error-msg {
    color: red;
  }
</style>
