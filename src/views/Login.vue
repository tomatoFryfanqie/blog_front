<template>
  <div>
    <LoginComponent msg="Hello" />
  </div>
</template>

<script>
// @ is an alias to /src
//import HelloWorld from "@/components/HelloWorld.vue";
import LoginComponent from "../components/LoginComponent.vue";

export default {
  name: "Login",
  components: {
    LoginComponent,
  },
};
</script>
