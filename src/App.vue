<template>
  <div id="app">
    <el-dialog
      title="BP设置"
      :visible.sync="setttingFlag"
      :close-on-click-modal="false"
      :show-close="false"
      :close-on-press-escape="false"
    >
      <el-form label-width="120px" label-position="right">
        <el-form-item label="Ban位数量">
          <el-input-number v-model="banNumber" controls-position="right" style="width: 100%;"></el-input-number>
        </el-form-item>
        <el-form-item label="Pick位数量">
          <el-input-number v-model="pickNumber" controls-position="right" style="width: 100%;"></el-input-number>
        </el-form-item>
      </el-form>
      <div style="text-align: right;">
        <el-button type="primary" @click="setttingFlag = false">确定</el-button>
      </div>
    </el-dialog>
    <ban-pick-selector :banNumber="banNumber" :pickNumber="pickNumber"/>
  </div>
</template>

<script>
import BanPickSelector from './components/BanPickSelector.vue'

export default {
  name: 'App',
  components: {
    BanPickSelector
  },
  data() {
    return {
      setttingFlag: true,
      banNumber: 6,
      pickNumber: 8,
    }
  },
  methods: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
