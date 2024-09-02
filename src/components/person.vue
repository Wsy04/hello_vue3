<template>
    <div class="person">
        <h2>姓名:{{ man.name }}</h2>
        <h2>年龄:{{ man.age }}</h2>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>
        <button @click="showTel">查看联系方式</button>
        <br>
        <h2>游戏列表</h2>
        <ul>
            <li v-for="g in games" :key="g.id">{{ g.name }}</li>
        </ul>
        <button @click="changeFirstName">修改第一个游戏的名字</button>
        <button @click="changeGame">修改游戏</button>
    </div>
</template>

<script lang="ts" setup name="person1">
    import {reactive, ref} from 'vue'
    //data
    let man = ref({name:'张三',age:18,tel:'1388888888'})
    let games = reactive([
        {id:'aguk01',name:'三国杀'},
        {id:'aguk02',name:'王者荣耀'},
        {id:'aguk03',name:'黑神话:悟空'}
    ])
    //method
    function changeName(){
        man.value.name+= 'zhangsan'
    }
    function changeAge(){
        man.value.age+=1
    }
    function showTel(){
        alert(man.value.tel)
    }
    function changeFirstName(){
        games[0].name = '原神'
    }
    function changeGame(){
        Object.assign(games[0],{id:'aguk04',name:'柚子社'})
    }

</script>

<style scoped>
    .person{
        background-color: skyblue;
        box-shadow: 0 0 10px;
        border-radius: 10px;
        padding: 20px;  
    }
    button{
        margin: 0 5px;
    }
    li{
        font-size: 20px;
    }
</style>