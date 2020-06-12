<template>
  <form class="row" @submit.prevent="onSubmit">
      <label for="amount">Le Mountant
      </label>
      <input type="number" min="30000" class="u-full-width" autocomplete="off" v-model="amount" />
      <input type="submit" class="button-primary" value="Calculez" />
    </form>
</template>

<script>
import {v4 as uuid} from 'uuid';

export default {
  name: 'search',
  data() {
    return {
      amount: '',
    };
  },
  methods: {
    calcIrg(x) {
      if (x < 30000) {
        return 'err';
      }
      return ((x - 30000) * 2) / 10;
    },
    onSubmit() {
      if(!this.amount ==''){
      const data = {
          id: uuid(),
          amount: this.amount,
          irg: this.calcIrg(parseInt(this.amount, 10)),
        };
        this.$emit('new-data', data, true);
      }else {
        const err = {
          msg : 'Entre le mountant SVP',
          err : true
          }
        this.$emit('new-err', err);
      }
      this.amount = '';
    },
  },
};
</script>

<style>

</style>
