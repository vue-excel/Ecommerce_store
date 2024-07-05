<template>
  <div class="nav-container">
    <router-link to="/">
      <div class="logo">Shazz</div>
    </router-link>
    <a-input-search
      placeholder="input search text"
      enter-button
      style="width: 250px"
      @search="onSearch"
      v-model="searchTerm"
    />
    <router-link to="/cart">
      <a-badge :count="allProductLength">
        <a href="#" class="head-example" />
        <a-icon
          type="shopping-cart"
          :style="{ fontSize: '20px', marginTop: '3px' }"
        />
      </a-badge>
    </router-link>
  </div>
</template>