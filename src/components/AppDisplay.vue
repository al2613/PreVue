<template>
  <div id="displayBox">
    <ComponentDisplay />
    <SideBar />
  </div>
</template>

<script>
import ComponentDisplay from './ComponentDisplay.vue';
import SideBar from './SideBar.vue';

export default {
  name: 'AppDisplay',

  components: {
    SideBar,
    ComponentDisplay
  }
};
</script>

<style scoped></style>
