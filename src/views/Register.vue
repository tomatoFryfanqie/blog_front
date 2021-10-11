<template>
  <div>
    <RegisterComponent msg="Vue" />
  </div>
</template>

<script>
import RegisterComponent from "../components/RegisterComponent.vue"
  export default{
    name : "Register",
    components : {
      RegisterComponent
    }
  }
</script>