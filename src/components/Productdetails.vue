<template>
  <div class="product-item">
    <img :src="product.image" />
    <div class="product-list">
      <p>{{ product.title }}</p>
      <span class="price">Цена: {{ formattedPrice }}</span>
      <p v-if="product.status" class="product-availability">Наличие: много</p>
      <p v-else class="product-availability">Продано</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductDetails",

  data() {
    return {
      product: {
        title: "Маленькое черное платье",
        price: 99.99,
        status: false,
        image: require("../assets/dress.jpeg"),
      },
    };
  },
  computed: {
    formattedPrice: function () {
      return `$${this.product.price}`;
    },
  },
};
</script>

<style scoped>
* {
  box-sizing: border-box;
}
.product-item {
  margin-top: 40px;
  width: 300px;
  text-align: center;
  margin: 0 auto;
  border-bottom: 2px solid #f5f5f5;
  background: white;
  font-family: "Open Sans";
  border: 2px solid #fc5a5a;
}
.product-item:hover {
  border-bottom: 2px solid #fc5a5a;
}
.product-item img {
  display: block;
  width: 100%;
}
.product-list {
  background: #fafafa;
  padding: 15px 0;
}
.product-list p {
  font-size: 22px;
  font-weight: 700;
  color: #444444;
  margin: 0 0 10px 0;
}
.price {
  font-size: 20px;
  color: #fc5a5a;
  display: block;
  margin-bottom: 12px;
}
</style>

Вы разрабатываете приложение для интернет-магазина и у вас есть компонент Vue под
названием "ProductDetails". Компонент отображает детали о конкретном продукте, включая его
название, цену и статус доступности. Внутри компонента "ProductDetails" создайте свойство
"product" с объектом, представляющим информацию о продукте. Объект должен иметь свойства
"name" (название продукта), "price" (цена продукта) и "available" (флаг, указывающий на
доступность продукта). Используя вычисляемое свойство, назовите его "formattedPrice",
которое будет возвращать форматированную цену продукта со знаком валюты. Например, если
цена равна 99.99, вычисляемое свойство должно вернуть строку "$99.99". В компоненте
"ProductDetails" отобразите название продукта, его форматированную цену и статус
доступности. Если продукт доступен, отобразите текст "Available", в противном случае -
"Out of stock".
