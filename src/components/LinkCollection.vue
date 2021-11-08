<template>
  <div class="col-md-8 col-sm-12 link-collections">
    <div class="row">
      <div
        :key="link_holder.id"
        v-for="link_holder in link_collection"
        class="col-sm-12 col-md-3 link-collection about"
      >
        <h4>{{ link_holder.title }}</h4>
        <ul class="nav flex-column">
          <li
            :key="link.label"
            v-for="link in link_holder.links"
            class="nav-item"
          >
            <a class="nav-link" aria-current="page" href="#"
              >{{ link.label }}
            </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "LinkCollection",
  props: {
    link_collection: Array,
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
@import "../styles/colors.scss";
@import "../styles/fonts.scss";

.link-collections {
  .link-collection {
    margin-bottom: 20px;
    ul.nav {
      li.nav-item {
        a.nav-link {
          color: $muted-text-color;
          font-family: $font-regular;
          font-size: 0.88rem;
          line-height: 1.88rem;
          padding: 0;
          &:hover {
            color: $link-color;
          }
        }
      }
    }
  }
}
</style>
