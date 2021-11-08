<template>
  <div class="content">
    <Hero />
    <Features />
    <Blogs :blogs="blogs" />
  </div>
</template>

<script>
import Hero from "./Hero";
import Blogs from "./Blogs";
import Features from "./Features";
import axios from "axios";
import data_backup from "../../public/data/data.json";

export default {
  name: "Header",
  components: {
    Hero,
    Blogs,
    Features,
  },
  data() {
    return {
      blogs: [],
    };
  },
  methods: {
    async fetchBlogs() {
      try {
        const res = await axios.get("/data/data.json");
        const data = await res.data;
        return data;
      } catch (error) {
        console.log(error);
        return data_backup;
      }
    },
  },

  async created() {
    this.blogs = await this.fetchBlogs();
  },
};
</script>
<style lang="scss" scoped>
</style>
