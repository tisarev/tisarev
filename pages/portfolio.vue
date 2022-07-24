<template>
      <section class="HomePortfolio container section">
        <h2>Многолетний опыт работы помогает находить лучшие решения в каждом конкретном случае, любой проект — это возможность повысить собственный уровень.</h2>
        <div v-for="item of list" :key="item.id" class="HomePortfolio__list">
            <div class="HomePortfolio__list-item">
                <img :src="require(`~/assets/img/mini/${item.small_img}`)">
                <div class="HomePortfolio__list-item__text">
                    <h3>{{item.title}}</h3>
                    <div class="HomePortfolio__list-item__text-gray">{{item.type_name}}</div>
                    <div class="HomePortfolio__list-item__text-black">{{item.text}}</div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>

export default{
    layout: 'portfolioList',
    layout (context) {
        return 'portfolioList'
    },
    async asyncData({ $axios }) {
        const list = await $axios.$get('http://api.tisarev.ru/posts')
        return {list}
    },
    data:  () => ({
        list: []
    })
};
</script>