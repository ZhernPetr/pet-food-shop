<script>
export default{
  name: 'App',

  data(){
    return {
      products: [
        {
          id:1,
          name: 'Корм для кошек',
          desc: 'Влажный корм со вкусом курицы',
          price: 150,
          image: 'https://avatars.mds.yandex.net/i?id=befd4bc21ee520af37da67afca2c16645bbfc0f2-12911696-images-thumbs&n=13'
        },
        {
          id:2,
          name: 'Корм для собак',
          desc: 'Сухой корм со вкусом ягнёнка',
          price: 2200,
          image: 'https://static.onlinetrade.ru/img/items/m/karmy_hypoallergenic_medium_maxi_yagnenok_dlya_sobak_srednikh_i_krupnykh_porod_14_kg_2052698_1.png'
        }
      ]
    }
  }
}
</script>

<template>
  <section class="catalog">
    <div class="product-card" v-for="product in products" :key="product.id">
      <img :src="product.image" :alt="product.name">
      <h2>{{ product.name }}</h2>
      <p>{{ product.desc }}</p>
      <p class="price">{{ product.price }}</p>
      <button>Подробнее</button>

    </div>
  </section>
</template>



<style scoped>

</style>