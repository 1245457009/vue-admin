<template>
    <!-- 必须要有一层父元素 -->
    <div id="login">
        <!-- 内容区 -->
        <div class="login-wrap">
            <ul class="menu-tab">
                <li @click="toggleMenu(item)" :class="{ 'current': item.current }" v-for="item in menuTab" :key="item.id">{{ item.txt }}</li>
            </ul>
        </div>
    </div>
</template>
<script>
export default{
    name: 'login', 
    data(){
        return{
            menuTab: [
                { txt: "登录", current: true }, 
                { txt: "注册", current: false }
            ], 
            isActive: true
        }
    }, 
    created(){}, 
    mounted(){}, 
    methods: {
        //数据驱动视图
        //js操作DOM元素
        toggleMenu(data){
            this.menuTab.forEach(element => {
                element.current = false;
            });
            data.current = true
        }
    }
}
</script>
// scoped是局部，只针对当前文件
<style lang="scss" scoped>
#login {
    height: 100vh;
    background-color: #344a5f;
}
.login-wrap {
    width: 330px;
    margin: auto;
}
.menu-tab{
    text-align: center;
    li {
        display: inline-block;
        width: 88px;
        line-height: 36px;
        font-size: 14px;
        color: #fff;
        border-radius: 2px;
        cursor: pointer;
    }
    .current {
        background-color: rgba($color: #000000, $alpha: .1);
    }
}
</style>