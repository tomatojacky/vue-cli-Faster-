<template>
    <div class="header">
        <div class="logo">优化打包 空模板</div>
        <div class="user-info">
            <el-dropdown trigger="click" @command="handleCommand">
                <span class="el-dropdown-link">
                    {{username}}
                </span>
                <el-dropdown-menu slot="dropdown">
                    <el-dropdown-item command="loginout">退出</el-dropdown-item>
                </el-dropdown-menu>
            </el-dropdown>
        </div>
    </div>
</template>
<script>
  export default {
    data () {
      return {
        name: 'linxin'
      }
    },
    computed: {
      username () {
        let username = localStorage.getItem('ms_username')
        return username || this.name
      }
    },
    methods: {
      handleCommand (command) {
        if (command === 'loginout') {
          localStorage.removeItem('ms_username')
          this.$router.push('/login')
        }
      }
    }
  }
</script>
<style scoped>
    .header {
        position: relative;
        box-sizing: border-box;
        width: 100%;
        height: 65px;
        font-size: 20px;
        line-height: 65px;
        color: #fff;
    }
    .header .logo{
        float: left;
        width:250px;
        height: 65px;
        text-align: center;
        text-indent: 170px;
    }
    .user-info {
        float: right;
        padding-right: 50px;
        font-size: 16px;
        color: #fff;
    }
    .user-info .el-dropdown-link{
        position: relative;
        display: inline-block;
        padding-left: 50px;
        color: #fff;
        cursor: pointer;
        vertical-align: middle;
    }
    .user-info .user-logo{
        position: absolute;
        left:0;
        top:15px;
        width:40px;
        height:40px;
        border-radius: 50%;
    }
    .el-dropdown-menu__item{
        text-align: center;
    }
</style>
