<template>
  <div id="app" class="container">
    <Header />
    <div class="dashboard-wrapper">
      <Dashboard />
    </div>
  </div>
</template>

<script>
import Header from '@/components/organisms/Header';
import Dashboard from '@/components/organisms/Dashboard';

export default {
  name: 'App',
  components: {
    Header,
    Dashboard,
  },
  data() {
    return {
      
    };
  },
  methods: {

  }
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap');
@import "@/styles/scss/_variable.scss";

html {
  box-sizing: border-box;
  font-family: 'Inter', sans-serif;
  font-size: 62.5%; // 10px
}

body {
  margin: 0;
  color: #fff;
  background: #fff;
}

*,
*::before,
*::after {
  box-sizing: inherit;
}

h1, h2, h3, h4, h5, h6 {
  margin: 0;
  font-weight: normal;
  font-size: 100%;
}

ul, dl, dd, p, figure {
  margin: 0;
  padding: 0;
}
.dashboard-wrapper {
  margin-top: 40px;
}
.container {
  background: $bg-dashboard;
  padding: 40px 150px;
  min-height: 100vh;
}
@media only screen and (max-width: 1000px) {
  .container {
    padding: 40px
  }
}
</style>