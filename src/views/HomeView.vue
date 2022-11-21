<script lang="ts">
import { defineComponent } from 'vue';
import { evaluate } from 'mathjs';

const operatorsRegex = /[*|\/|-|+]/g;

export default defineComponent({
  name: 'HomeView',
  data() {
    return {
      result: '',
      shouldReset: false,
    }
  },
  methods: {
    lastResultChar(): string {
      return '';
    },
    provideValue(value: string): void {},
    solve(): void {},
    clear(): void {},
    clearEnd(): void {} 
  },
  computed: {
    shouldDisableOperatorSign(): boolean {
      return false;
    }
  }
});
</script>

<template>
  <div id="calculator-container">
    <table id="calculator-table">
      <tbody>
        <tr>
          <td colspan="4"><input type="text" v-bind:value="result"></td>
        </tr>
        <tr>
          <td colspan="3"><input type="button" value="C"></td>
          <td><input type="button" value="CE"></td>
        </tr>
        <tr>
          <td><input type="button" value="1"></td>
          <td><input type="button" value="2"></td>
          <td><input type="button" value="3"></td>
          <td><input type="button" value="/"></td>
        </tr>
        <tr>
          <td><input type="button" value="4"></td>
          <td><input type="button" value="5"></td>
          <td><input type="button" value="6"></td>
          <td><input type="button" value="*"></td>
        </tr>
        <tr>
          <td><input type="button" value="7"></td>
          <td><input type="button" value="8"></td>
          <td><input type="button" value="9"></td>
          <td><input type="button" value="-"></td>
        </tr>
        <tr>
          <td><input type="button" value="0"></td>
          <td><input type="button" value="."></td>
          <td><input type="button" value="="></td>
          <td><input type="button" value="+"></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>
#calculator-container {
  display: flex;
  align-items: center;
  justify-content: center;
}

#calculator-table {
  border: 0.025rem solid #494949;
  background-color: #b2b2b2;
  margin-left: auto;
  margin-right: auto;
  border-radius: 0.5rem;
}

input[type="button"] {
  width: 100%;
  padding: 0.25rem 0.5rem;
  background-color: #5e5e5e;
  color: white;
  font-size: 24px;
  font-weight: bold;
  border: 0.025rem solid #b2b2b2;
  border-radius: 0.5rem;
}

input[type="button"]:disabled {
  background-color: #7c7c7c;
  color: #b2b2b2;
}

input[type="text"] {
  padding: 0.25rem 0.5rem;
  font-size: 24px;
  font-weight: bold;
  border: none;
  border-radius: 0.5rem;
  border: 0.025rem solid #3e3e3e;
}
</style>