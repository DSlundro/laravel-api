<template>
    <div class="posts bg-col">
        <h2>Tags</h2>
        <div class="container">
            <div class="row flex-column m-auto">
                <div class="col" v-for="tag in tags" :key="tag.id">
                    <h4>#{{tag.name}}</h4>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Tags',
    props: ['tags'],
}
</script>

<style lang="scss" scoped>

</style>