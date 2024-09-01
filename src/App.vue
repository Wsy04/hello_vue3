<template>
    <!-- html结构 -->
    <person/>

</template>

<script>
    // js或者ts
    import person from './components/person.vue';
    export default{
        name:'App',
        components:{person}//注册组件
    }
</script>

