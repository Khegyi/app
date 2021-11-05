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
      <div class="col-md-4 col-sm-12 subscribtion">
        <div class="subscribe-form">
          <h4>Subscribe to the newsletter</h4>
          <form>
            <div class="row">
              <div class="col-sm-12 col-xxl-6">
                <input type="text" id="first_name" placeholder="First name" />
              </div>
              <div class="col-sm-12 col-xxl-6">
                <input type="text" id="last_name" placeholder="Last name" />
              </div>
            </div>
            <div class="row">
              <div class="col">
                <input type="email" id="email" placeholder="Email" />
              </div>
            </div>
            <div class="row">
              <div class="col">
                <input
                  @click="onSubmit"
                  class="btn btn-primary"
                  id="subscribe_btn"
                  type="submit"
                  value="Subscribe"
                />
              </div>
            </div>
            <div class="row">
              <div class="col">
                <p class="error-message"></p>
              </div>
            </div>
          </form>
        </div>
      </div>
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
export default {
  name: "Footer",
  props: {
    msg: String,
  },
  methods: {
    scrollTop(e) {
      e.preventDefault();
      $(document).scrollTop(0);
    },
    onSubmit(e) {
      e.preventDefault();
      const firstName = $("#first_name").val();
      const lastName = $("#last_name").val();
      const email = $("#email").val();
      if (firstName !== "" && lastName !== "" && email !== "") {
        $(".error-message").text("").hide();
      } else {
        $(".error-message").text("All field must be filled out!").show();
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
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
    .subscribtion {
      .subscribe-form {
        h4 {
          margin-bottom: 20px;
        }
        form {
          input {
            width: 100%;
            transition: box-shadow 0.5s;
            &:focus {
              box-shadow: 2px 2px 3px #2929296e;
            }
            &:focus-visible {
              border-radius: 0;
              outline: 0px solid $main-color;
            }
            &[type="text"],
            &[type="email"] {
              border: 1px solid $input-border-color;
              font-family: $font-regular;
              font-size: 0.88rem;
              line-height: 1.13rem;
              padding: 12px 16px;
              margin-bottom: 20px;
            }
            &::placeholder {
              color: $input-placeholder-color;
              font-family: $font-regular;
              font-size: 0.88rem;
              line-height: 1.13rem;
            }
          }

          .btn {
            border-radius: 0;
            border: 0;
            background-color: #000;
            font-family: $font-semibold;
            font-size: 1rem;
            line-height: 1.75rem;
            &:hover {
              background-color: $main-color;
            }
          }
          .error-message {
            display: none;
            margin: 15px 0;
            font-family: $font-semibold;
            color: $error-color;
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
