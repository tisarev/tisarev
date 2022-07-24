<template>
    <div class="page">
        <div class="wrapper">
            <HomeBanner />
            <Nuxt />
        </div>
        <TheFooter />
        <Sprite />
    </div>
</template>

<script>
import TheFooter from '~/components/TheFooter.vue';
import Sprite from '~/components/Sprite.vue';

export default{
    components: { TheFooter, Sprite }
};
</script>