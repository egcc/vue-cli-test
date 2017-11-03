<template>
  <div>
    <h3>this is a child components.</h3>
    <p>this is a parent value:<span style="color:red;">这是普通字符串:{{propText}}</span></p>
    <p><span style="color:red;">这是动态prop:{{propTwo}}</span></p>
    <p>这是数值&prop作为初始值:{{initValue}} 计算属性：{{initValueAddFive}}</p>
    <p>prop时的类型：{{missType}}</p>
    <hr/>
    <p>api data: {{dataList}}</p>
    <p><input type="button" value="getData" v-on:click="getApiData"></p>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  props: ['propText', 'propTwo', 'numProp'],
  data () {
    return {
      initValue: this.numProp,
      missType: typeof this.numProp,
      dataList: []
    }
  },
  computed: {
    initValueAddFive: function () {
      return this.initValue + 5
    }
  },
  methods: {
    getApiData: function () {
      axios.get('http://localhost:8080/api/books').then((res) => {
        this.dataList = res.data
      })
    }
  }
}
</script>

<style>
  hr{
    border: none;
    height: 1px;
    background-color: red;
  }
</style>