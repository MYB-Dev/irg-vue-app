<template>
  <div>
    <table v-if="showTable" class="u-full-width">
        <thead>
          <tr>
            <th>Le Mountant</th>
            <th>L' IRG</th>
            <th></th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in data" :key="item.amount">
            <td>{{ item.amount }},00 DA</td>
            <td>{{ item.irg }},00 DA</td>
            <td><button class="del" @click="$emit('delete-item', item.id)">X</button></td>
          </tr>
        </tbody>
      </table>
      <div class="p" v-if="error.err && !showTable">
        <p>⚠️ {{error.msg}} ⚠️</p>
      </div>
    </div>
</template>

<script>
export default {
  name: 'Result',
  props: ['data', 'error', 'showTable'],
  methods:{}
};
</script>

<style scoped>
  .p{
    font-size: 2.5rem;

    color: #cf5c60;
  }
  .del{
  display: inline-block;
  height: 20px;
  padding: 0 15px;
  text-align: center;
  font-size: 11px;
  font-weight: 600;
  line-height: 18px;
  letter-spacing: 0.1rem;
  text-transform: uppercase;
  text-decoration: none;
  white-space: nowrap;
  border-radius: 4px;
  border: 1px solid;
  cuitemor: pointer;
  box-sizing: border-box;
  color: #fff;
  background-color: #ef6a6e;
  border-color: #ef6a6e;
  justify-content: left;
  text-align: left;
}
</style>
