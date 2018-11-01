<template>
  <div id="home">
    <h1>Web3 Online Tools</h1>
    <p>
      Online web3 tools using
      <a href="https://web3js.readthedocs.io/en/1.0/index.html" target="_blank" rel="noopener">web3.js</a>
      for support your dapps development
    </p>
    <p><a href="https://github.com/sapuri/web3-online-tools" target="_blank" rel="noopener">GitHub repository</a></p>

    <ToChecksumAddress/>
    <CheckAddressChecksum/>
  </div>
</template>

<script>
  import ToChecksumAddress from './ToChecksumAddress.vue'
  import CheckAddressChecksum from './CheckAddressChecksum.vue'

  export default {
    name: 'home',
    components: {
      ToChecksumAddress,
      CheckAddressChecksum
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .result {
    color: green;
  }

  .error-msg {
    color: red;
  }
</style>
