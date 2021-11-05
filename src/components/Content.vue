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
export default {
  name: "Header",
  components: {
    Hero,
    Blogs,
    Features,
  },
  props: {
    msg: String,
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
      }
    },
  },

  async created() {
    this.blogs = await this.fetchBlogs();
  },
};
</script>
<style lang="scss" scoped>
@import "../styles/colors.scss";
@import "../styles/fonts.scss";

.content {
  .hero {
    margin-bottom: 25px;
    img.pattern {
      width: 100%;
      position: absolute;
      z-index: -1;
      object-fit: cover;
      height: 700px;
      top: 0;
    }
    .card {
      margin: 0 auto;
      border: none;
      background-color: unset;
      .hero-text {
        display: flex;
        align-items: center;
        .card-body {
          h5.card-title {
            max-width: 461px;
            font-size: 3.13rem;
            line-height: 3.88rem;
            color: $maintext-color;
            font-family: $font-bold;
            margin-bottom: 30px;
            .goldplating {
              color: $link-color;
            }
          }
          .card-text {
            max-width: 440px;
            font-size: 1rem;
            line-height: 1.75rem;
            color: $subtext-color;
            font-family: $font-regular;
            margin-bottom: 40px;
            strong {
              font-family: $font-bold;
            }
          }
        }
      }
      .card-btn {
        border-radius: 0;
        border: 0;
        background-color: #000;
        width: 220px;
        font-family: $font-semibold;
        font-size: 1rem;
        line-height: 1.75rem;
        &:hover {
          background-color: $main-color;
        }
        &:focus {
          box-shadow: none;
        }
      }
      .hero-watch-holder {
        overflow: hidden;
        .hero-watch-img {
          position: relative;
          z-index: 1;
        }
        .hero-watch-white-bg {
          width: 197px;
          height: 504px;
          background-color: rgba(#fff, 0.1);
          position: absolute;
          z-index: 0;
          top: 35px;
        }
      }
    }
  }
  .features {
    background-color: $main-color;
    color: white;
    min-height: 177px;
    position: relative;
    .row.wrap {
      height: 100%;
      margin: 0 auto;
      .feature {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 45px 0 37px;
        .feature_icon {
          flex: 1;
        }
        label {
          margin-top: 20px;
          font-family: $font-semibold;
          font-size: 1.13rem;
          line-height: 1.38rem;
        }
        &:last-child {
          border-right: none;
        }
      }
    }
  }
  .blogs {
    padding: 50px 0 49px 0;
    border-bottom: 1px solid rgba($nav-color, 0.15);
    background-color: #fff;
    .card-group {
      margin: 0 auto;
      .card {
        border: 1px solid rgba($main-color, 0.1);
        margin-right: 28px;
        border-radius: 0;
        .card-content {
          display: flex;
          height: 100%;
          flex-direction: column;
          .card-body {
            padding: 20px 20px 0 20px;
            .card-title {
              color: $subtext-color;
              font-family: $font-bold;
              font-size: 1.13rem;
              line-height: 1.75rem;
            }
          }
          .card-footer {
            background-color: #fff;
            border: none;
            padding: 30px 20px;
            a.nav-link {
              color: $link-color;
              font-family: $font-medium;
              font-size: 1rem;
              line-height: 1.19rem;
              display: flex;
              align-items: center;
              padding: 0;
            }
            img.arrow_icon {
              margin-left: 10px;
            }
          }
        }
        transition: box-shadow 0.5s;
        &:hover {
          box-shadow: 2px 2px 3px #2929296e;
        }
      }
      :last-child {
        margin-right: 0;
      }
    }
  }
}
</style>
