<template>
  <div id="to-checksum-address">
    <md-card>
      <md-card-header>
        <div class="md-title">toChecksumAddress</div>
      </md-card-header>

      <md-card-content>
        <pre>web3.utils.toChecksumAddress(address)</pre>
        <p class="description">Will convert an upper or lowercase Ethereum address to a checksum address.</p>
        <div>
          <md-field>
            <label>address</label>
            <md-input v-model="address"></md-input>
            <span class="md-helper-text">String: An address string.</span>
          </md-field>
          <p v-if="result" class="result">Result: {{ result }}</p>
          <p v-if="errorMsg" class="error-msg">{{ errorMsg }}</p>
        </div>
      </md-card-content>

      <md-card-actions>
        <md-button v-on:click="run">Run</md-button>
      </md-card-actions>
    </md-card>
  </div>
</template>

<script>
  import Vue from 'vue'
  import {MdCard, MdField} from 'vue-material/dist/components';
  import * as web3 from "web3";

  Vue.use(MdCard);
  Vue.use(MdField);

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
