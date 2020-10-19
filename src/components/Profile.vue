<template>
  <div class="profile">
    <img class="profile__image" src="/assets/baris.jpg" alt="Profile Image" />
    <h1  class="profile__name">{{profileName}}</h1>
    <h2  class="profile__subheading">{{location}}</h2>

    <div class="profile__stats">
      <ProfileStats 
       v-for="(stat, index) in profileStats"
       :key="index"
       :stat="stat"></ProfileStats>
    </div>

  </div>
</template>

<script>
import ProfileStats from './ProfileStats';

export default {
  name: 'Profile',
  props: {
    profileName: String,
    location: String,
  },
  components: {
    ProfileStats,
  },
  data() {
    return{
      profileStats: [
        {
          count: "100",
          text:  "Posts",
        },
        {
          count: "2,242",
          text:  "Follower",
        },
        {
          count: "1,432",
          text:  "Following",
        },
      ],
    };
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
// *****************
// * Style Imports *
// *****************
@import "../scss/variables";
@import "../scss/globals";
@import "../scss/mixins";

// *******************
// * Profile Section *
// *******************
.profile{
  margin: 0;
  padding-top: 42px;

  justify-content: center;
  align-content: center;
  text-align: center;

  // * Profile Image Styling * //
  &__image{
    width: 100px;
    height: 100px;
    border-radius: 38px;

    // * Desktop Media Query * // 
    @include breakpoint(s){
      width: 156px;
      height: 156px;
      border-radius: 60px;
    }
  }

  // * Profile Name Styling * //
  &__name{
    padding-top: 12px;

    font-size: $profile-mobile;
    line-height: 16px;

    // * Tablet Media Query * // 
    @include breakpoint(xs){
      font-size: $profile-tablet;
    }

    // * Desktop Media Query * // 
    @include breakpoint(s){
      font-size: $profile-desktop;
    }
  }

  // * Profile Location Styling * //
  &__subheading{
    font-size: $subheading-mobile;
    color: $gray-second;
    line-height: 12px;

    // * Desktop Media Query * //
    @include breakpoint(s){
      font-size: $subheading-desktop;
    }
  }


  &__stats{
    display: flex;
    flex-direction: row;

    margin-top: 12px;
    
    @include breakpoint(s){
      margin-top: 24px;
    }

    // * Center Alignment * //
    justify-content: center;
    align-items: center;
  }
}

</style>
