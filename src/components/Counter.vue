<template>
  <div>
    <span class="price"> Total Price: {{ (product.price * value).toFixed(2) }} </span>
    <br />
    <a-button
      @click="subtractFromCounter(product)"
      type="primary"
      shape="circle"
    >
      -
    </a-button>
    {{ value }}
    <a-button @click="addToCounter(product)" type="primary" shape="circle">
      +
    </a-button>
    <br />
    <a-button v-show="value > 0" type="primary" @click="addToCart()">
      Add to cart
    </a-button>
    <a-button v-show="value > 0" type="danger" @click="removeFromCart()">
      Remove From cart
    </a-button>
  </div>
</template>


<style scoped>
.counter {
  font-size: 5rem;
}
.ant-btn {
  margin: 12px 0;
}
.ant-btn-danger {
  margin-left: 10px !important;
}
.price {
  color: orange;
  font-size: 20px;
}
</style>
