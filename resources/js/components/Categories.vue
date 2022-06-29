<template>
    <div class="posts bg-col">
        <h2>Categories</h2>
        <div class="container">
            <div class="row flex-column m-auto">
                <div class="col" v-for="category in categories" :key="category.id">
                    <h4>{{category.name}}</h4>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Categories',
    props: ['categories'],
}
</script>

<style lang="scss" scoped>

</style>