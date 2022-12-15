<template>
  <ul class="navigation">
    <li class="navigation__logo">
      <a href="#home" aria-label="go to dog world home">
        <img
          :src="require('../assets/img/dog-world-logo.svg')"
          alt="Dog Word Logo"
        />
      </a>
    </li>
    <li class="navigation__links-container">
      <div class="navigation__hamburger" @click="toggleMenu">
        <img
          :src="require('../assets/img/icon-hamburger.svg')"
          alt="hamburger icon"
        />
      </div>
      <ul class="navigation__links" :class="hideMenu ? 'mobile-hide' : ''">
        <li class="navigation__link">
          <a href="#" aria-label="home">Home</a>
        </li>
        <li class="navigation__link">
          <a href="#about-us" aria-label="about us">About us</a>
        </li>
        <li class="navigation__link">
          <a href="#pricing" aria-label="pricing">Pricing</a>
        </li>
      </ul>
    </li>
    <li class="navigation__button">
      <a href="#lets-talk" aria-label="let's talk">Let's Talk </a>
    </li>
  </ul>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    const hideMenu = ref(true);

    const toggleMenu = () => {
      hideMenu.value = !hideMenu.value;
    };
    return {
      toggleMenu,
      hideMenu,
    };
  },
};
</script>

<style lang="scss" scoped>
$copper: #9a6d4a;
$white: #ffffff;
$dark-gray: #333333;
.navigation {
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-content: center;
  list-style: none;
  margin: 0;
  padding: 0;
  background-color: $white;
  &__logo {
    flex: 1;
  }
  &__links-container {
    flex: 4;
  }
  &__links {
    list-style: none;
    padding: 0;
    a {
      color: $dark-gray;
    }
    display: flex;
    flex-direction: column;
    align-content: center;
  }
  &__link {
    padding: 16px;
    font-weight: 500;
    font-size: 16px;
  }
  &__button {
    display: inline-block;
    padding: 16px 28px;
    background-color: $copper;
    border-radius: 30px;
    font-weight: 500;
    a {
      color: $white;
    }
  }
}
.mobile-hide {
  display: none;
}
@media screen and (min-width: 768px) {
  .navigation {
    max-width: 1170px;
    margin: auto;
    &__hamburger {
      display: none;
    }
    &__links {
      display: inline-block;
      flex-direction: row;
      justify-content: flex-end;
      margin-right: 50px;
    }
    &__link {
      padding: 10px;
    }
  }
  .mobile-hide {
    display: flex;
  }
}
</style>
