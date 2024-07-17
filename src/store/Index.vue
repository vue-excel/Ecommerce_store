import Vue from 'vue';
import Vuex from 'vuex';

Vue.use(Vuex);

export default new Vuex.Store({
    state: {
    cart: [],
    items: [],
  },

  mutations: {
    setItems(state, payload) {
      state.items = payload;
    },
    sortAscendingAction(state) {
      state.items = state.items.sort(function (a, b) {
        return a.price - b.price;
      });
    },
    sortDescendingAction(state) {
      state.items = state.items.sort(function (a, b) {
        return b.price - a.price;
      });
    },
    addProductToCart(state, payload) {
      let check = true;

      state.cart.forEach((element) => {
        if (element.id === payload.id) {
          element.value = payload.value;
          check = false;
        }
      });
      if (check) {
        state.cart.push(payload);
      }
    },
    removeProductToCart(state, id) {
      if (!id) {
        return;
      }
      state.cart = [...state.cart.filter((v) => v.id !== id)];
    },
    increaseCount(state, id) {
      state.cart.forEach((element) => {
        if (element.id === id) {
          element.value++;
        }
      });
    },
    decreaseCount(state, id) {
      state.cart.forEach((element) => {
        if (element.id === id) {
          if (element.value > 0) {
            element.value--;
          }
          if (element.value === 0) {
            this.commit('removeProduct', id);
          }
        }
      });
    },
    removeProduct(state, id) {
      if (!id) {
        return;
      }
      state.cart = [...state.cart.filter((v) => v.id !== id)];
    },
    clearCart(state) {
      console.log('inside clearing cart');

      state.cart = [];
    },
  },
});
