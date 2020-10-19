<template>
  <div id="app">
    <Profile 
    :profileName="`Baris Tikir`" 
    :location="`Berlin Germany`"/>

    <Portfolio :Images="images"/>
  </div>
</template>

<script>
import Profile from './components/Profile.vue'
import Portfolio from './components/Portfolio.vue'

export default {
  name: 'App',
  components: {
    Profile,
    Portfolio,
  },
  data() {
    return{
      images: [
        {
          row: "1",
          column: "1",
          size: "small",
          path: "/assets/photo1.png",
        },
        {
          row: "1",
          column: "2",
          size: "big",
          path: "/assets/photo2.png",
        },
        {
          row: "2",
          column: "1_2",
          size: "big",
          path: "/assets/photo3.png",
        },
        {
          row: "3",
          column: "1",
          size: "small",
          path: "/assets/photo6.png",
        },
        {
          row: "3",
          column: "2",
          size: "small",
          path: "/assets/photo5.png",
        },
        {
          row: "2_4",
          column: "3",
          size: "height",
          path: "/assets/photo4.png",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
@import "./scss/variables";
@import "./scss/globals";
@import "./scss/mixins";
</style>
