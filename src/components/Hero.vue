<template>
  <section class="hero">
    <img class="pattern" src="../assets/images/background_pattern.png" alt="" />
    <div class="dark-hero-bg">
      <p class="dark-hero-text">CHRISTOPHER WARD</p>
    </div>
    <div class="card breakpoint-changer">
      <div class="row g-0">
        <div class="col-sm-5 col-9 hero-text">
          <div class="card-body">
            <h5 class="card-title">
              The message is a simple.
              <span class="goldplating">That's It.</span>
            </h5>
            <p class="card-text">
              This is watch maintains their signature aesthetic as it pushes the
              <strong>boundaries of design possibility.</strong> Despite its
              almost effortless appearance, Seconds is the result of a careful
              and <strong>imaginative creative process.</strong>
            </p>
            <a href="#" class="btn btn-primary card-btn">Buy now</a>
          </div>
        </div>
        <div class="col-sm-7 col-6 hero-watch-holder">
          <div
            src="../assets/images/hero_watch.png"
            class="hero-watch-img"
            alt="hero watch"
          ></div>
          <div class="hero-watch-white-bg"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Hero",
  methods: {},
};
</script>

<style lang="scss" scoped>
@import "../styles/colors.scss";
@import "../styles/fonts.scss";

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
  .dark-hero-bg {
    background-color: $dark-hero-bg-color;
    position: absolute;
    height: 700px;
    right: 0;
    top: 0;
    z-index: -1;
    overflow: hidden;
    .dark-hero-text {
      opacity: 0.2;
      font-family: $font-black;
      font-size: 13.75rem;
      line-height: 11.25rem;
      color: $maintext-color;
      text-align: left;
      margin-top: 200px;
      margin-left: 65px;
    }
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
        background-image: url("~@/assets/images/hero_watch.png");
        z-index: 1;
        height: 567px;
        width: 459px;
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
</style>
