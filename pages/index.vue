<template lang="pug">
    <div>
        nuxt-link(to="index") index
        nuxt-link(to="about") about
        nuxt-content(:document="docs")
    </div>
</template>
<script>
export default {
    async asyncData({$content, params}){
        const docs = await $content(params.pathMatch || 'index').fetch()

        console.log(docs);
        return {docs}
    }
}
</script>
<style scoped>
    a{
        padding: 0 50px;
        color: #fff;
        background-color: red;
    }
</style>