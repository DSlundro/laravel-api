<template>
    <div class="posts bg-col">
        <h2>Posts</h2>
        <div class="container">
            <div class="row row-cols-3 gap-2">
                <div class="col" v-for="post in posts" :key="post.id">
                    <div class="card my-3">
                        <img :src="post.cover_image" alt="">
                        <div class="card-body">
                            <h4 class="card-title"><b>{{post.title}}</b></h4>
                            <h6>{{post.category}}</h6>
                            <p>{{post.content.slice(0, 100)}}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Posts',
    props: ['posts'],
    mounted() {
        console.log('Component mounted.')
    }
}
</script>

<style lang="scss" scoped>

</style>