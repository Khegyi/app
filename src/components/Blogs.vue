<template>
  <section class="blogs">
    <div class="row card-group breakpoint-changer">
      <div :key="blog.title" v-for="blog in blogs" class="col-sm-12 card p-0">
        <img :src="blog.image" class="card-img-top" alt="watch" />
        <div class="card-content">
          <div class="card-body">
            <h5 class="card-title">{{ blog.title }}</h5>
          </div>
          <div class="card-footer">
            <a class="nav-link" href="#"
              >Read more
              <img
                src="../assets/icons/arrow.svg"
                class="arrow_icon"
                alt="arrow icon"
              />
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Blogs",
  props: {
    blogs: Array,
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
@import "../styles/colors.scss";
@import "../styles/fonts.scss";

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
</style>
