<template>
    <!-- ======= Hero Section ======= -->
  <section id="hero">
    <div class="row m-0">
      <div class="col-10">
        <Posts 
        :posts="posts"/>
      </div>
      <div class="col-2">
        hello
      </div>
    </div>
  </section><!-- End Hero -->
  
</template>

<script>
import Posts from '../components/Posts.vue';

export default {
    name: 'App',
    components: { Posts },
    data(){
      return {
        posts: [],
      }
    },
    created(){
      console.log(this.posts);
    },
    mounted(){
      axios
      .get('/api/posts')
      .then((response) => {
        console.log(response.data.data);
        this.posts = response.data.data
      })
    }
}

</script>

<style land="scss" scoped>
#hero {
  width: 100%;
  height: 100%;
  background: url("hero-bg.jpg") top center;
  background-size: cover;
  background-attachment: fixed;
  position: relative;
  /* countdown */
}

</style>