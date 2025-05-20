<script>

import ProductCard from './components/ProductCard.vue';


export default{
  
  name: 'App',

  components: {
    ProductCard
  },

  data() {
    return {
      products: [
        {
          id:1,
          name: 'Whiskas',
          desc: 'Влажный корм со вкусом курицы',
          price: 150,
          image: 'https://avatars.mds.yandex.net/i?id=befd4bc21ee520af37da67afca2c16645bbfc0f2-12911696-images-thumbs&n=13',
          type: 'wet',
          animal:'cat'
        },
        {
          id:2,
          name: 'Karmy',
          desc: 'Сухой корм со вкусом ягнёнка',
          price: 2200,
          image: 'https://static.onlinetrade.ru/img/items/m/karmy_hypoallergenic_medium_maxi_yagnenok_dlya_sobak_srednikh_i_krupnykh_porod_14_kg_2052698_1.png',
          type: 'dry',
          animal:'dog'
        },
        {
          id:3,
          name: 'ABBA',
          desc: 'Влажный корм (консервы) для взрослых собак всех пород, говядина, с ягненком и голубикой',
          price: 375,
          image: 'https://4lapy.ru/_next/image/?url=https%3A%2F%2Fstorage.yandexcloud.net%2Fpim-core%2F370250.jpeg&w=1080&q=70',
          type: 'wet',
          animal:'dog'
        },
        {
          id:4,
          name: 'Grandin',
          desc: 'Влажный корм (консервы) для взрослых собак всех пород, с ягненком и льняным маслом',
          price: 165,
          image: 'https://4lapy.ru/_next/image/?url=https%3A%2F%2Fstorage.yandexcloud.net%2Fpim-core%2F369815.jpeg&w=1080&q=75',
          type: 'wet',
          animal:'dog'
        },
        {
          id:5,
          name: 'ABBA',
          desc: 'Влажный корм (консервы) для взрослых собак всех пород, с кроликом с рисом',
          price: 375,
          image: 'https://4lapy.ru/_next/image/?url=https%3A%2F%2Fstorage.yandexcloud.net%2Fpim-core%2F370019.jpeg&w=1080&q=75',
          type: 'wet',
          animal:'dog'
        },
        {
          id:6,
          name: 'Royal Canin Mini',
          desc: 'Влажный корм (пауч) для собак мелких пород',
          price: 103,
          image: 'https://4lapy.ru/_next/image/?url=https%3A%2F%2Fstorage.yandexcloud.net%2Fpim-core%2F374927.jpeg&w=1080&q=75',
          type: 'wet',
          animal:'dog'
        },
        {
          id:7,
          name: 'Whiskas',
          desc: 'Влажный корм Whiskas для кошек аппетитный микс говядина язык и овощи в желе прошут',
          price: 163,
          image: 'https://avatars.mds.yandex.net/get-mpic/6240175/img_id7627745761664298548.jpeg/optimize',
          type: 'wet',
          animal:'cat'
        },
        {
          id:8,
          name: 'Karmy',
          desc: 'Влажный корм Karmy STERILIZED Лосось в желе для стерилизованных кошек и кастрированных котов старше 1 года',
          price: 800,
          image: 'https://avatars.mds.yandex.net/get-mpic/4012096/2a0000018df5364d87a50b26bbd76e2a3068/optimize',
          type: 'wet',
          animal:'cat'
        },
        {
          id:9,
          name: 'Chappi',
          desc: 'Корм для собак сухой Chappi говядина по-домашнему, с овощами, с травами',
          price: 3200,
          image: 'https://avatars.mds.yandex.net/get-mpic/6982353/img_id4478331554605745222.jpeg/optimize',
          type: 'dry',
          animal:'dog'
        },
        {
          id:10,
          name: '',
          desc: 'Chappi сухой корм для взрослых собак всех пород, говядина по-домашнему',
          price: 682,
          image: 'https://avatars.mds.yandex.net/get-mpic/7650323/img_id3904429663626658291.jpeg/optimize',
          type: 'dry',
          animal:'dog'
        },
        {
          id:11,
          name: 'Whiskas',
          desc: 'Сухой корм Whiskas для кошек «Подушечки с паштетом. Ассорти с курицей и индейкой»',
          price: 1700,
          image: 'https://avatars.mds.yandex.net/get-mpic/12258964/img_id8172734259326321286.jpeg/optimize',
          type: 'dry',
          animal:'cat'
        },
        {
          id:12,
          name: 'Whiskas',
          desc: 'Корм сухой для стерилизованных кошек Whiskas с курицей',
          price: 500,
          image: 'https://avatars.mds.yandex.net/get-mpic/4571152/img_id2755752639219699923.jpeg/optimize',
          type: 'dry',
          animal:'cat'
        }
      ]
    }
  }
}
</script>

<template> <!--вёрстка, html--> 
  <header>
            <h1>Каталог кормов для животных</h1>

            <!--Поиск в каталоге-->
            <div class="search-bar">                    
                <input type="text" placeholder="Введите название товара"/>
                <button type="submit">Найти</button>
            </div>

            <!--Фильтрация каталога-->
            <div class="filters">
                <!--Фильтр по животному-->
                <label for="animal">Животное:</label>
                <select name="animal" id="animal">
                    <option value="">Все</option>
                    <option value="cat">Кошки</option>
                    <option value="dog">Собаки</option>
                </select>
                
                <!--фильтр по виду корма-->
                <label for="type">Тип корма:</label>
                <select name="type" id="type">
                    <option value="">Все</option>
                    <option value="dry">Сухой</option>
                    <option value="wet">Влажный</option>
                </select>
            </div>

            

        </header>

  <section class="catalog">
    <ProductCard v-for="product in products" :key="product.id" :product="product" />
    <!-- v for перебирает массив products, products="product" передают объект в props, :key="product.id" отслеживакет изменения -->
  </section>
</template>



<style scoped> /* стиль, CSS*/

</style>