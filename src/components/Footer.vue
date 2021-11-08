<template>
  <footer>
    <div class="row wrap breakpoint-changer">
      <LinkCollection :link_collection="link_collection" />
      <SubscriptionForm />
    </div>
    <div id="scroll-top" class="row mx-0 lifter">
      <div class="col">
        <a @click="scrollTop" class="nav-link" nohref>
          <img
            class="chevron_icon"
            width="25"
            src="../assets/icons/right_chevron_icon.svg"
            alt=""
          />
        </a>
      </div>
    </div>
  </footer>
</template>

<script>
import $ from "jquery";
import SubscriptionForm from "./SubscriptionForm.vue";
import LinkCollection from "./LinkCollection.vue";
export default {
  name: "Footer",
  components: {
    SubscriptionForm,
    LinkCollection,
  },
  data() {
    return {
      link_collection: [
        {
          title: "About",
          links: [
            { label: "Introduction", href: "" },
            { label: "Loremipsum", href: "" },
            { label: "Brands sold", href: "" },
            { label: "Conditions of use", href: "" },
            { label: "Impressum", href: "" },
            { label: "Contact", href: "" },
          ],
        },
        {
          title: "Information",
          links: [
            { label: "Help to purchasing", href: "" },
            { label: "Purchasing information", href: "" },
            { label: "Pay and delivery", href: "" },
            { label: "FAQ", href: "" },
            { label: "Data protection", href: "" },
            { label: "Conditions", href: "" },
          ],
        },
        {
          title: "Follow me!",
          links: [
            { label: "Newsletter", href: "" },
            { label: "Facebook", href: "" },
            { label: "Google Plus", href: "" },
            { label: "Twitter", href: "" },
          ],
        },
      ],
    };
  },
  methods: {
    scrollTop(e) {
      e.preventDefault();
      $(document).scrollTop(0);
    },
  },
};
</script>

<style lang="scss">
@import "../styles/colors.scss";
@import "../styles/fonts.scss";

footer {
  padding-top: 40px;
  background-color: #fff;
  .wrap {
    margin: 0 auto;
    margin-bottom: 40px;
    padding: 0 20px;
    h4 {
      color: $maintext-color;
      font-family: $font-bold;
      font-size: 0.88rem;
      line-height: 1.13rem;
      margin-bottom: 11px;
    }
  }
  .lifter {
    border-top: 1px solid rgba($nav-color, 0.15);
    height: 53px;
    cursor: pointer;
    .nav-link {
      height: 100%;
      display: flex;
      justify-content: center;
      img.chevron_icon {
        transform: rotate(-90deg);
      }
    }
    transition: background-color 0.5s;
    &:hover {
      background-color: rgba($main-color, 0.1);
    }
  }
}
</style>
