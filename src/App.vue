<template>
  <AppHeader />
  <div class="w-full flex">
    <!-- <DcHeros /> -->
    <AppCalender />
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AppCalender from "./components/AppCalender.vue";
// import DcHeros from "./components/DcHeros.vue";

export default {
  components: {
    AppHeader,
    AppCalender,
  },
};
</script>
