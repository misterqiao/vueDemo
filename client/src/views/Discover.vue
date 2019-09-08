<template>
  <div class="find">
    <Header title="发现"/>
  </div>
</template>
<script>
import Header from "../components/Header";
export default {
  name: "discover",
  data() {
    return {};
  },
  components: {
    Header
  }
};
</script>

<style scoped>
.find {
  width: 100%;
  height: calc(100% - 55px);
  position: relative;
  box-sizing: border-box;
}
.content {
  width: 100%;
  height: calc(100% - 50px);
  margin-top: 50px;
}
</style>