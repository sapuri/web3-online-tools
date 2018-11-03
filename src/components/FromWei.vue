<template>
  <div id="from-wei">
    <md-card>
      <md-card-header>
        <div class="md-title">fromWei</div>
      </md-card-header>

      <md-card-content>
        <pre>web3.utils.fromWei(number [, unit])</pre>
        <p class="description">Converts any wei value into a ether value.</p>
        <div>
          <md-field>
            <label>number</label>
            <md-input v-model="number" type="number"></md-input>
            <span class="md-helper-text">String|Number|BN: The value in wei.</span>
          </md-field>
          <md-field>
            <label>unit</label>
            <md-input v-model="unit"></md-input>
            <span class="md-helper-text">String (optional, defaults to "ether"): The ether to convert to.</span>
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
