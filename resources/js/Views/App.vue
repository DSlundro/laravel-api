<template>
    <!-- ======= Hero Section ======= -->
  <section id="hero">
    <div class="row m-0 pt-5">

      <div class="col-10">
        <Posts :posts="posts"/>
      </div>
      <div class="col-2">
        <div class="d-flex">
          <Categories :categories="categories"/>
          <Tags :tags="tags"/>
        </div>
      </div>
    </div>
  </section><!-- End Hero -->
  
</template>

<script>
import Categories from '../components/Categories.vue';
import Posts from '../components/Posts.vue';
import Tags from '../components/Tags.vue';

export default {
    name: 'App',
    components: { Posts, Categories, Tags },
    data(){
      return {
        posts: [],
        categories: [],
        tags: [],
      }
    },
    created(){
      this.getPosts();
      this.getCategories();
      this.getTags();
    },
    methods:{
      getPosts(){
        axios.get('/api/posts').then((response) => {
          this.posts = response.data.data
          // console.log(this.posts);
        })
      },
      getCategories(){
        axios.get('/api/categories').then((response) => {
          this.categories = response.data.data
          // console.log(this.categories);
        })
      },
      getTags(){
        axios.get('/api/tags').then((response) => {
          this.tags = response.data.data
          console.log(this.tags);
        })
      },
    }
}

</script>

<style land="scss">
#hero {
  width: 100%;
  height: 100%;
  background: url("hero-bg.jpg") top center;
  background-size: cover;
  background-attachment: fixed;
  position: relative;
}
#hero > .row{
  padding: 0 50px;
}
.my-container{
  max-width: 1300px;
}
.bg-col{
    background-color: rgba(255, 255, 255, 0.6) !important;
    backdrop-filter: blur(5px);
    margin: 10px !important;
    padding: 25px 0 !important;
    border-radius: 15px !important;
    box-shadow: 0 0 30px rgba(0, 0, 0, 0.548);
}
h2{
    border-bottom: 2px solid rgba(128, 128, 128, 1);
    padding-bottom: 18px !important;
    font-size: 35px !important;
    text-align: center !important;
}

</style>