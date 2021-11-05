<template>
  <header class="breakpoint-changer">
    <nav class="navbar navbar-expand-lg p-0">
      <div class="container-fluid p-0">
        <a class="navbar-brand p-0" href="#">
          <img src="../assets/logos/logo.svg" class="logo" alt="front logo" />
        </a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"
            ><img
              class="hamburger_icon"
              src="../assets/icons/hamburger_icon.svg"
              alt="hamburger icon"
          /></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav">
            <li class="nav-item">
              <a class="nav-link" href="#">Shop</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Collection</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Accessories</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Gift guide</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Blog</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Contact</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style lang="scss" scoped>
@import "../styles/colors.scss";
@import "../styles/fonts.scss";
header {
  margin: 0 auto;
  margin-bottom: 25px;
  nav {
    background-color: #fff;
    .navbar-brand {
      margin: 23px 40px;
      height: 36px;
      img.logo {
        height: 36px;
      }
    }
    #navbarNav {
      justify-content: flex-end;
      ul.navbar-nav {
        li.nav-item .nav-link {
          color: $nav-color;
          font-family: $font-bold;
          font-size: 1.13rem;
          line-height: 1.38rem;
          padding: 30px 20px;
          &:hover {
            color: $link-color;
          }
        }
      }
    }
    button.navbar-toggler {
      margin-right: 20px;
      padding: 0;
      &:focus {
        box-shadow: 0 0 0 0.1rem;
      }
    }
  }
}
</style>
