<template>
    <div class="portfolio">
        <div
         v-for="(image, index) in Images"
         :key="index"
         :image="image"
         :class="[image.size]">

                <img 
                 :class="[image.size,'row-' + image.row, 'col-' + image.column]"
                 :src="`${image.path}`"
                  alt="" />

         </div>
    </div>
</template>

<script>
export default {
    props: {
        Images: Array,
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

// *********************
// * Portfolio Section *
// *********************
.portfolio{
    display: grid;

    margin-top: 2rem;
    margin-left: 12px;
    margin-right: 12px;

    max-width: 351px;

    grid-template-rows: repeat(auto-fit, repeat(3, 1fr));
    justify-content: center;

    grid-template-columns: repeat(3, 6.6rem);
    column-gap: 0.8rem;
    row-gap: 0.7rem;

    @include breakpoint(s){
        margin-top: 3rem;
        margin-left: 240px;
        margin-right: 240px;
        max-width: 960px;

        grid-template-columns: repeat(3, 18.3rem);
        column-gap: 1.8rem;
        row-gap: 1rem;
    }
    .small {
        width: 110px;
        height: 110px;
        border-radius: 20px;

        @include breakpoint(s){
            width: 299px;
            height: 299px;
            border-radius: 20px;
        }
    }

    .big {
        width: 229px;
        height: 110px;
        border-radius: 20px;

        @include breakpoint(s){
            width: 629px;
            height: 299px;
            border-radius: 20px;
        }
    }

    .height{
        width: 108px;
        height: 230px;
        border-radius: 20px;

        @include breakpoint(s){
            width: 297px;
            height: 630px;
            border-radius: 20px;
        }
    }
    // ***************** //
    // * Helper Classes* //
    // ***************** //
    .row-1{
        grid-row: 1;
    }
    .row-2{
        grid-row: 2;
    }
    .row-3{
        grid-row: 3;
    }
    .row-2_4{
        grid-row: 2 / 4;
    }

    .col-1{
        grid-column: 1;
    }
    .col-2{
        grid-column: 2;
    }
    .col-3{
        grid-column: 3;
    }
    .col-1_2{
        grid-column: 1 / 2;
    }

}
</style>