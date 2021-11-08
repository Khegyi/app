<template>
  <div class="col-md-4 col-sm-12 subscription">
    <div class="subscribe-form">
      <h4>Subscribe to the newsletter</h4>
      <form @submit.prevent="submit">
        <div class="row">
          <div
            class="form-group col-sm-12 col-xxl-6"
            :class="{ 'form-group--error': $v.firstName.$error }"
          >
            <input
              type="text"
              id="first_name"
              placeholder="First name"
              v-model.trim.lazy="$v.firstName.$model"
            />
            <div class="error" v-if="!$v.firstName.required">
              First name is required
            </div>
          </div>
          <div
            class="form-group col-sm-12 col-xxl-6"
            :class="{ 'form-group--error': $v.lastName.$error }"
          >
            <input
              type="text"
              id="last_name"
              placeholder="Last name"
              v-model.trim.lazy="$v.lastName.$model"
            />
            <div class="error" v-if="!$v.lastName.required">
              Last name is required
            </div>
          </div>
        </div>
        <div class="row">
          <div
            class="form-group col"
            :class="{ 'form-group--error': $v.email.$error }"
          >
            <input
              type="text"
              id="email"
              placeholder="Email"
              v-model.trim.lazy="$v.email.$model"
            />
            <div class="error" v-if="!$v.email.required">Email is required</div>
            <div class="error" v-if="!$v.email.email">
              Must be a valid email
            </div>
          </div>
        </div>
        <div class="row">
          <div
            class="col form-group"
            :class="{ 'form-group--error': submitStatus }"
          >
            <input
              class="btn btn-primary"
              id="subscribe_btn"
              type="submit"
              value="Subscribe"
            />
            <p class="typo__p ok" v-if="submitStatus === 'OK'">
              Thanks for your submission!
            </p>
            <p class="typo__p error" v-if="submitStatus === 'ERROR'">
              Please fill the form correctly.
            </p>
            <p class="typo__p pending" v-if="submitStatus === 'PENDING'">
              Sending...
            </p>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import Vuelidate from "vuelidate";
import { required, email } from "vuelidate/lib/validators";

Vue.use(Vuelidate);

export default {
  name: "SubscriptionForm",
  data() {
    return {
      firstName: "",
      lastName: "",
      email: "",
      submitStatus: null,
    };
  },
  validations: {
    firstName: {
      required,
    },
    lastName: {
      required,
    },
    email: {
      required,
      email,
    },
  },
  methods: {
    submit() {
      this.$v.$touch();
      if (this.$v.$invalid) {
        this.submitStatus = "ERROR";
      } else {
        this.submitStatus = "PENDING";
        setTimeout(() => {
          this.submitStatus = "OK";
        }, 500);
      }
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
.subscription {
  .subscribe-form {
    h4 {
      margin-bottom: 10px;
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
          margin: 10px 0;
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
        margin: 10px 0;
        background-color: #000;
        font-family: $font-semibold;
        font-size: 1rem;
        line-height: 1.75rem;
        &:hover {
          background-color: $main-color;
        }
      }
      .form-group--error {
        animation-name: shakeError;
        animation-fill-mode: forwards;
        animation-duration: 0.6s;
        animation-timing-function: ease-in-out;
        .error {
          display: block;
        }
        input {
          border-color: $error-color;
        }
      }
      .error {
        display: none;
        color: $error-color;
        font-size: 0.8rem;
        font-family: $font-regular;
      }
    }
  }
}
</style>
