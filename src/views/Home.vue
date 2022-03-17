<template>
  <div>
    <input :type="toggle" placeholder="Password" />
    <span @click="visibility" class="icon">
      <font-awesome-icon :icon="eyeIcon" size="lg" />
    </span>
  </div>
</template>

<script>
import { faEye, faEyeSlash } from "@fortawesome/free-solid-svg-icons";
export default {
  data() {
    return {
      showPassword: false,
    };
  },
  computed: {
    eyeIcon() {
      return this.showPassword ? faEye : faEyeSlash;
    },
    toggle() {
      return this.showPassword ? "password" : "text";
    },
  },
  methods: {
    visibility() {
      return (this.showPassword = !this.showPassword);
    },
  },
};
</script>

<style scoped>
.icon {
  background-color: rgb(233, 229, 229);
  border-radius: 3px;
  cursor: pointer;
  padding: 10px;
}
input {
  display: inline;
  padding: 8px;
  width: 20%;
}
</style>
