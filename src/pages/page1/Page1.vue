<template lang="html">
  <div class="page">
    <h1 v-text="hello"></h1>
    <div class="vuex-example">
      <h2>Vuex Example</h2>
      <button @click="decrement"><i class="el-icon-minus"></i></button>
      <span v-text="count"></span>
      <button @click="increment"><i class="el-icon-plus"></i></button>
    </div>
  </div>
</template>

<script type="ts">
  import { mapGetters, mapActions } from 'vuex';

  export default {
    data() {
      return {
        hello: 'Hello World',
        count: 0,
      };
    },
    computed: {
      ...mapGetters({
        countNum: 'count',
      }),
    },
    methods: {
      ...mapActions({
        increment: 'increment',
        decrement: 'decrement',
      }),
    },
    watch: {
      countNum(val) {
        this.count = val;
        console.log(val);
      },
    },
  };
</script>

<style lang="scss" scoped>
  .page {
    h1 {
      text-align: center;
      color: #ff0000;
    }

    .vuex-example {
      margin: 200px auto;
      text-align: center;
      font-size: 16px;
      color: #fff;

      span {
        font-size: 28px;
        display: inline-block;
        margin-left: 20px;
        margin-right: 20px;
      }

      button {
        cursor: pointer;
        border: none;
        width: 44px;
        height: 44px;
        outline: none;
        font-size: 20px;
        font-weight: bold;
        border-radius: 50%;
        background-color: #fff;
      }
    }
  }
</style>
