<template>
  <div class="hero interior">
    <div class="hero__content">
      <div class="hero__message">
        <h1 class="hero__message-header">Welcome to Our Fantastic Website</h1>
        <p class="hero__message-copy">
          Scroll down to learn a little more about us, see our pricing, and fill
          out the form. Or you could just fill out the form at the top of the
          page; no need to actually read anything.
        </p>
      </div>
      <div class="hero__form-container">
        <DogWorldForm />
      </div>
    </div>
  </div>
</template>
<script>
import DogWorldForm from "./DogWorldForm.vue";
export default {
  components: {
    DogWorldForm,
  },
  setup() {},
};
</script>

<style lang="scss">
$white: #ffffff;
.hero {
  &__content {
    background: linear-gradient(
        360deg,
        rgba(34, 20, 10, 0.7) 0%,
        rgba(0, 0, 0, 0.11) 100%
      ),
      url("../assets/img/hero-background.jpg");
    display: flex;
    flex-direction: row;
    padding-left: 135px;
    padding-right: 135px;
  }
  &__message {
    margin-top: 160px;
    margin-bottom: 200px;
    color: $white;
    flex: 1;
    text-align: left;
  }
  &__message-header {
    font-weight: 700;
    font-size: 56px;
    line-height: 66px;
  }
  &__message-copy {
    font-weight: 400;
    font-size: 20px;
    line-height: 30px;
  }
  &__form-container {
    flex: 1;
    margin-top: 92px;
    margin-bottom: 70px;
    border-radius: 15px;
    overflow: hidden;
    margin-left: 200px;
  }
}
</style>
