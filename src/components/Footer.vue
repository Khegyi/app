<template>
  <footer>
    <div class="row wrap breakpoint-changer">
      <div class="col-md-8 col-sm-12 link-collections">
        <div class="row">
          <div class="col-sm-12 col-md-3 link-collection about">
            <h4>About</h4>
            <ul class="nav flex-column">
              <li class="nav-item">
                <a class="nav-link" aria-current="page" href="#"
                  >Introduction
                </a>
              </li>
              <li class="nav-item">
                <a class="nav-link" aria-current="page" href="#">Loremipsum</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" aria-current="page" href="#">Brands sold</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" aria-current="page" href="#"
                  >Conditions of use</a
                >
              </li>
              <li class="nav-item">
                <a class="nav-link" aria-current="page" href="#">Impressum</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" aria-current="page" href="#">Contact</a>
              </li>
            </ul>
          </div>
          <div class="col-sm-12 col-md-3 link-collection information">
            <h4>Information</h4>
            <ul class="nav flex-column">
              <li class="nav-item">
                <a class="nav-link" aria-current="page" href="#"
                  >Help to purchasing</a
                >
              </li>
              <li class="nav-item">
                <a class="nav-link" aria-current="page" href="#"
                  >Purchasing information</a
                >
              </li>
              <li class="nav-item">
                <a class="nav-link" aria-current="page" href="#"
                  >Pay and delivery</a
                >
              </li>
              <li class="nav-item">
                <a class="nav-link" aria-current="page" href="#">FAQ</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" aria-current="page" href="#"
                  >Data protection</a
                >
              </li>
              <li class="nav-item">
                <a class="nav-link" aria-current="page" href="#">Conditions</a>
              </li>
            </ul>
          </div>
          <div class="col-sm-12 col-md-3 link-collection follow-me">
            <h4>Follow me!</h4>
            <ul class="nav flex-column">
              <li class="nav-item">
                <a class="nav-link" aria-current="page" href="#">Newsletter</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" aria-current="page" href="#">Facebook</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" aria-current="page" href="#">Google Plus</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" aria-current="page" href="#">Twitter</a>
              </li>
            </ul>
          </div>
        </div>
      </div>
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

export default {
  name: "Footer",
  components: {
    SubscriptionForm,
  },
  methods: {
    scrollTop(e) {
      e.preventDefault();
      $(document).scrollTop(0);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../styles/colors.scss";
@import "../styles/fonts.scss";

@keyframes shakeError {
  0% {
    transform: translateX(0);
  }
  15% {
    transform: translateX(0.375rem);
  }
  30% {
    transform: translateX(-0.375rem);
  }
  45% {
    transform: translateX(0.375rem);
  }
  60% {
    transform: translateX(-0.375rem);
  }
  75% {
    transform: translateX(0.375rem);
  }
  90% {
    transform: translateX(-0.375rem);
  }
  100% {
    transform: translateX(0);
  }
}

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
