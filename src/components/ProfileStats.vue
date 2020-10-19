<template>
    <div class="profile__stat">

        <div class="profile__stat-number">
            {{stat.count}}
        </div>

        <div class="profile__stat-text">
            {{stat.text}}
        </div>

    </div>
</template>

<script>
export default {
    props: {
        stat: Object,
    },
};
</script>

<style lang="scss" scoped>
// *****************
// * Style Imports *
// *****************
@import "../scss/variables";
@import "../scss/globals";
@import "../scss/mixins";

// *************************
// * Profile Stats Section *
// *************************
.profile__stat{
    margin-right: 24px;
    background-color: $gray-card;

    width: 78px;
    height: 52px;
    border-radius: 12px;
    
    &:last-child{
        margin-right: 0;
    }

    @include breakpoint(s){
        width: 100px;
        height: 67px;
        border-radius: 16px;
    }

    &-number{
        margin-top: 14px;
        font-size: $normal-count-mobile;

        @include breakpoint(s){
            font-size: $normal-count-desk;
        }
    }

    &-text{
        font-size: $normal-text-mobile;

        @include breakpoint(s){
            font-size: $normal-text-desk;
        }
    }
}
</style>