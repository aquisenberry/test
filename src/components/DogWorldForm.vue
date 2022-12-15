<template>
  <div class="dog-form" :class="heroForm ? 'white' : 'none'">
    <form
      class="dog-form__form"
      :class="heroForm ? 'single-column' : 'two-column'"
      @submit="handleFormSubmit"
    >
      <input
        v-model="firstName"
        name="firstName"
        type="text"
        placeholder="First Name"
      />
      <input
        v-model="lastName"
        name="lastName"
        type="text"
        placeholder="Last Name"
      />
      <input
        v-model="phone"
        name="phone"
        type="tel"
        placeholder="Phone Number"
      />
      <input
        v-model="email"
        name="email"
        type="email"
        placeholder="Email Address"
      />
      <textarea v-model="message" name="message" placeholder="Message" />
      <input type="submit" value="Submit" />
    </form>
  </div>
</template>
<script>
import { ref, toRefs } from "vue";
export default {
  props: {
    heroForm: {
      type: Boolean,
      default: true,
    },
  },
  setup(props) {
    const heroForm = toRefs(props);
    const firstName = ref("");
    const lastName = ref("");
    const phone = ref("");
    const email = ref("");
    const message = ref("");
    const handleFormSubmit = (e) => {
      e.preventDefault();

      let validated = handleValidation();

      if (validated) {
        const formSubmission = {
          form: heroForm ? "Hero Form" : "contact form",
          firstName: firstName.value,
          lastName: lastName.value,
          phone: phone.value,
          email: email.value,
          message: message.value,
        };

        console.log(formSubmission);
      }
    };

    const handleValidation = () => {
      const validationCheck = [];

      validationCheck.push(firstName.value.length > 0);
      validationCheck.push(lastName.value.length > 0);
      validationCheck.push(/^[0-9-+()\s]+$/.test(phone.value));
      validationCheck.push(
        /^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?(?:\.[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?)*$/.test(
          email.value
        )
      );
      // if any of our validation checks have failed, flag it as failing
      return !validationCheck.includes(false);
    };
    return {
      handleFormSubmit,
      firstName,
      lastName,
      phone,
      email,
      message,
    };
  },
};
</script>

<style lang="scss">
$white: #ffffff;
$copper: #9a6d4a;
.dog-form {
  &.white {
    background-color: $white;
  }
  &__form {
    display: flex;
    flex-direction: column;
    padding: 30px;
    &.single-column {
      font-size: 14px;
      line-height: 30px;
      font-weight: 300;
      input,
      textarea {
        padding: 10px 10px 10px 20px;
        border-radius: 5px;
        margin-bottom: 15px;
        height: 50px;
        border: 1px solid #cccccc;
      }
      textarea {
        height: 140px;
      }
      input[type="submit"] {
        height: 46px;
        background-color: $copper;
        color: $white;
        font-weight: 600;
        font-size: 16px;
        line-height: 16px;
      }
    }
    &.two-column {
      font-size: 14px;
      line-height: 30px;
      font-weight: 300;
      input,
      textarea {
        padding: 10px 10px 10px 20px;
        border-radius: 5px;
        margin-bottom: 20px;
        height: 50px;
        border: 1px solid #cccccc;
      }
      textarea {
        height: 140px;
      }
      input[type="submit"] {
        height: 46px;
        background-color: $copper;
        color: $white;
        font-weight: 600;
        font-size: 16px;
        line-height: 16px;
      }
    }
  }
}
</style>
