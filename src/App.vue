<script setup>
    import Button from '../src/components/Button.vue'
    import Img from '../src/components/Img.vue'
    import { ref } from 'vue'
    import { fadeTransition} from '../src/transitions.js'

    const showImage = ref(true)
    
</script>

<template>
    <div class="template">
        <Button class="!my-[20px]" @click="showImage = !showImage"></Button>
        <div class="img-container w-[800px]">
            <Transition v-bind="fadeTransition">
                <Img v-if="showImage"></Img>
            </Transition>
        </div>
    </div>
</template>

<style lang="scss">

    .template{
        @include flex;

        background-color: $primary;
        height: 100svh;
        flex-direction: column;
    }

    .img-container{
        display: flex;
        align-items: center;
        justify-content: center;
        height: 500px;
        outline: 2px solid yellow;
    }

</style>