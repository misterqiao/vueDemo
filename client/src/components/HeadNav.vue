<template>
    <header class="head-nav">
        <el-row>
            <el-col :span = "6" class = "logo-container">
                <img src = "../assets/logo.png" alt = "" class = "logo">
                <span class = "title">趣试衣在线后台管理系统</span>
            </el-col>
              <!-- <el-menu
                class="el-menu-demo"
                mode="horizontal"
                background-color="#324057"
                text-color="#fff"
                active-text-color="#ffd04b">
                <el-menu-item class="index1" index="1">处理中心</el-menu-item>
                <el-submenu class="index1" index="2">
                    <template slot="title">我的工作台</template>
                    <el-menu-item index="2-1">选项1</el-menu-item>
                    <el-menu-item index="2-2">选项2</el-menu-item>
                    <el-submenu index="2-4">
                    <template class="index1" slot="title">选项4</template>
                    <el-menu-item index="2-4-1">选项1</el-menu-item>
                    <el-menu-item index="2-4-2">选项2</el-menu-item>
                    <el-menu-item index="2-4-3">选项3</el-menu-item>
                    </el-submenu>
                </el-submenu> -->
                
                <!-- <el-menu-item class="index1" index="3">消息中心</el-menu-item>
           
                <el-submenu class="index1" index="4">
                    <template slot="title">个人中心</template>
                    <el-menu-item index="4-1">选项1</el-menu-item>
                    <el-menu-item index="4-2">选项2</el-menu-item>
                </el-submenu>
             </el-menu> -->

            <el-col :span = "6" class = "user">
               <div class="userinfo">
                   <img :src=" user.avatar " alt="" class="avatar">
                   <div class="welcome">
                       <p class="name comename">欢迎</p>
                        <p class="name avatarname">{{user.name}}</p>
                   </div>
                   <span class="username">
                       <el-dropdown trigger="click" @command= "setDialogInfo">
                        <span class="el-dropdown-link">
                            <i class="el-icon-caret-bottom el-icon--right"></i>
                        </span>
                        <el-dropdown-menu slot="dropdown">
                            <el-dropdown-item command="info">个人信息</el-dropdown-item>
                            <el-dropdown-item command="logout">退出</el-dropdown-item>
                        </el-dropdown-menu>
                        </el-dropdown>
                   </span>
               </div>
            </el-col>
        </el-row>
    </header>
</template>


<script>
export default {
    name: "head-nav",
    computed:{
        user(){
            return this.$store.getters.user;
        }
    },
  
    methods:{
        setDialogInfo(a){
            switch(a){
                case "info":
                    this.showInfoList();
                    break;
                case "logout":
                    this.logout();
                    break;
            }

        },
        showInfoList(){
           this.$router.push("/infoshow")
        },
        logout(){
            localStorage.removeItem("eleToken")
            this.$store.dispatch("logoutUser")
            this.$router.push("/login")
        }

    }
}
</script>

<style scoped>
.head-nav{
    width: 100%;
    height: 60px;
    min-width: 600px;
    padding: 5px;
    background: #324057;
    color:#fff;
    border-bottom: 1px solid #1f2d3d;
}
.el-menu-demo{
    display: inline-block;
}
.el-menu-demo .index1{
    border:none;
    height: 63px;

}
.username{
    cursor: pointer;
    margin-right: 5px;
}
.avatarname{
    color:#409eff;
    font-weight: bolder;
}
.comename{
    font-size: 12px;
}
.name{
    line-height: 20px;
    text-align: center;
    font-size: 14px;
}
.title{
    vertical-align: middle;
    font-size: 22px;
    font-family: "Microsoft YaHei";
    letter-spacing: 3px;

}
.logo{
    height: 50px;
    width: 50px;
    margin-right: 5px;
    vertical-align: middle;
    display: inline-block;
}
.avatar{
    width: 40px;
    height: 40px;
    border-radius: 50%;
    vertical-align: middle;
    display: inline-block;
}
.welcome{
    display: inline-block;
    width: auto;
    vertical-align: middle;
    padding: 0 5px;

}
.logo-container{
    line-height: 60px;
    min-width: 400px;
}
.user{
    line-height: 60px;
    text-align: right;
    float: right;
    padding-right: 10px;
}
.el-dropdown{
    color:#fff;
}
</style>