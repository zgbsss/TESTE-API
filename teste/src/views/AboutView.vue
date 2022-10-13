<script>
export default {
  data() {
    return {
      token: "dddd",
    };
  },
  methods: {
    getHashParams() {
      var hashParams = {};
      var e,
        r = /([^&;=]+)=?([^&;]*)/g,
        q = window.location.hash.substring(1);
      e = r.exec(q);
      while (e) {
        hashParams[e[1]] = decodeURIComponent(e[2]);
        e = r.exec(q);
      }
      return hashParams;
    },
  },
  created() {
    this.token = this.$route.query["code"];
    console.log(this.getHashParams(this.token));
  },
};
</script>
<template>
  <div class="about">
    <h1>This is an about page</h1>
    <h2>{{ token }}</h2>
  </div>
</template>

<style></style>
