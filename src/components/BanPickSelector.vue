<template>
    <div>
      <el-container class="BPHeader">
        <el-header class="BanHeader">
          <div class="BanHeaderLeft">
            <div class="BanItem" v-for="item in banNumber" :key="item"></div>
          </div>
          <div>title</div>
          <div class="BanHeaderRight">
            <div class="BanItem" v-for="item in banNumber" :key="item"></div>
          </div>
        </el-header>
      </el-container>
      <el-container class="BPBody">
        <el-aside class="PickLeft">
          <div v-for="item in pickNumber" class="pickItem" :key="item"></div>
        </el-aside>
        <el-container>
          <el-header class="classification">分类</el-header>
          <el-container class="cardBody">
            <div v-for="(card, index) in cardResource" :key="index" class="cardItem">
              <el-image :src="logo"></el-image>
            </div>
          </el-container>
        </el-container>
        <el-aside class="PickRight">
          <div v-for="item in pickNumber" class="pickItem" :key="item"></div>
        </el-aside>
      </el-container>
    </div>
</template>
  
<script>
import resource from './resource.js';
import logo from '../assets/logo.png';
export default {
    name: 'BanPickSelector',
    props: {
      pickNumber: {
        type: Number,
        default: 8
      },
      banNumber: {
        type: Number,
        default: 6
      }
    },
    data() {
      return {
        cardResource: resource,
        logo: logo
      }
    },
  }
</script>
  
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.BPHeader {
  height: 60px;
}

.BPBody {
  height: calc(100vh - 60px);
}

.BanHeader {
  display: flex;
  justify-content: space-between;
}

.BanHeaderLeft {
  display: flex;
  width: 300px;
}

.BanHeaderRight {
  display: flex;
  width: 300px;
}

.BanItem {
  width: calc(300px / v-bind(banNumber));
  background-color: black;
  height: 100%;
  border: solid 1px red;
}

>>> .el-header {
  padding: 0;
}

.PickLeft {
  background-color: red;
}

.PickRight {
  background-color: aqua;
}

.pickItem {
  border: 1px solid black;
  height: calc((100% - 2px * v-bind(pickNumber)) / v-bind(pickNumber));
}

.cardBody {
  border: 1px solid black;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
  justify-items: center;
  overflow: scroll;
}

.classification {
  text-align: left;
  height: 30px !important;
}

.cardItem {
  height: 120px;
  width: 120px;
  border: 1px solid goldenrod;
  margin-bottom: 30px;
}
</style>
  