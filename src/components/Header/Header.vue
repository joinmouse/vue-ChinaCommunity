<template lang="html">
  <div  class="header" :style="{backgroundColor: skinColor}">
    
    <!--topbar-->
    <div class="bar">
      <span class="aside">
        <i class="aside-icon"></i>
      </span>
      <p>云音乐</p>
      <span class="search">
        <i @click="toSearch" class="search-icon"></i>
      </span>
    </div>
    <!--tab-header-->
    <div class="tab">
      <div v-bind:class="{link: linkBorderIndex==1}" class="item">
        <router-link to="/music-list">我的</router-link>
      </div>
      <div v-bind:class="{link: linkBorderIndex==2}" class="item">
        <router-link to="/find">发现</router-link>
      </div>
      <div v-bind:class="{link: linkBorderIndex==3}" class="item">
        <router-link to="/social">一个</router-link>
      </div>
    </div>

  </div>
</template>

<script>
  export default {
    name: 'header'
  }
</script>

<style lang="scss" scoped>
  .header {
    background-color: #B72712;
    color: white;

    .bar {
      display: flex;
      justify-content: space-between;
      text-align: center;
      padding:10px 0;
      border-bottom: 1px solid rgba(255,255,255,0.2);
      span.aside {
        flex: 1;
        position: relative;
        i {
          display: inline-block;
          position: absolute;
          width: 20px;
          height: 20px;
          left: 15px;
          bottom: 0;
          background: url(./aside.svg) no-repeat;
          background-size: contain;
          cursor: pointer;
        }
      }

      p {
        flex: 1
      }
      span.search {
        flex: 1;
        position: relative;
        i {
          display: inline-block;
          position: absolute;
          width: 20px;
          height: 20px;
          right: 15px;
          bottom: 0;
          background: url(./search.svg) no-repeat;
          background-size: contain;
          cursor: pointer;
        }
      }
    }

    .tab {
      border-bottom: 1px solid #9e9e9e;
      display: flex;
      a {
        display: inline-block;
        width: 50%
      }
      a::after {
        height: 1px;
        bottom: -2px;
        background: rgba(255,255,255,0.2);
      }
      
      .item {
        display: inline-block;
        flex: 1;
        text-align: center;
        padding: 10px 0;
      }
      .link {
        font-weight: bold;
        color: #BDBDBD;
        border-bottom: 1px solid #E0F2F1;
      }
    }
  }
</style>

