<template>
  <section class="features">
    <div class="row wrap breakpoint-changer">
      <div class="col-6 col-md-3 feature">
        <img
          class="feature_icon"
          src="../assets/icons/leather_icon.svg"
          alt="leather_strap"
        />
        <label for="leather_strap">Leather Strap</label>
      </div>
      <div class="col-6 col-md-3 feature">
        <img
          class="feature_icon"
          src="../assets/icons/water_resistant.svg"
          alt="water_resistant"
        />
        <label for="water_resistant">Water resistant</label>
      </div>
      <div class="col-6 col-md-3 feature">
        <img
          class="feature_icon"
          src="../assets/icons/spring_drive_icon.svg"
          alt="spring_drive"
        />
        <label for="spring_drive"> Spring Drive</label>
      </div>
      <div class="col-6 col-md-3 feature">
        <img
          class="feature_icon"
          src="../assets/icons/warranty_icon.svg"
          alt="warranty"
        />
        <label for="warranty">Warranty</label>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Features",
  methods: {},
};
</script>

<style lang="scss" scoped>
@import "../styles/colors.scss";
@import "../styles/fonts.scss";

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
</style>
