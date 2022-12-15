<template>
  <div class="contact-us interior">
    <div class="contact-us__content">
      <div class="contact-us__message">
        <h2 class="contact-us__message-header">Contact Us</h2>
        <p class="contact-us__message-copy">
          Enter your info below and we’ll be in touch shortly.
        </p>
      </div>
      <div class="contact-us__form-container">
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
.contact-us {
  &__content {
    background: url("../assets/img/contact-background.jpg");
    display: flex;
    flex-direction: column;
    padding-left: 135px;
    padding-right: 135px;
  }
  &__message {
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
    border-radius: 15px;
    overflow: hidden;
    margin-left: 200px;
  }
}
</style>
