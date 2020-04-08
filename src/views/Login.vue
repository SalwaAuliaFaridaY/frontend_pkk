<template>
  <div class="limiter">
    <div class="container-login100" style=" background-image: url('img/applestore.jpg');">
      <div class="wrap-login100">
        <form class="login100-form validate-form">
          <span class="login100-form-logo">
            <img src="img/apple.png" alt width="90" height="110" />
          </span>

          <span class="login100-form-title p-b-34 p-t-27">Log in</span>

          <div class="wrap-input100 validate-input" data-validate="Enter email">
            <input class="input100" type="email" name="email" placeholder="Email" />
            <span class="focus-input100" data-placeholder="&#xf207;"></span>
          </div>

          <div class="wrap-input100 validate-input" data-validate="Enter password">
            <input class="input100" type="password" name="password" placeholder="Password" />
            <span class="focus-input100" data-placeholder="&#xf191;"></span>
          </div>

          <div class="container-login100-form-btn">
            <button class="login100-form-btn">Login</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "login",
  data() {
    return {
      email: "",
      password: ""
    };
  },
  methods: {
    Login: function() {
      let email = this.email;
      let password = this.password;
      this.$store
        .dispatch("login", { email, password })
        .then(() => this.$router.push("/"))
        .catch(err => console.log(err));
    }
  }
};
</script>