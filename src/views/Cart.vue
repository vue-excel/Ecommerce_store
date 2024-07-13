<template>
  <div style="padding: 50px 30px">
    <a-row :gutter="[50, 0]">
      <a-col
        :xl="{ span: 16 }"
        :lg="{ span: 16 }"
        :md="{ span: 12 }"
        :xs="{ span: 24 }"
      >
        <a-list
          class="demo-loadmore-list"
          item-layout="horizontal"
          :data-source="cart"
        >
          <a-list-item
            style="min-height: 150px"
            slot="renderItem"
            slot-scope="item"
          >
            <a-button
              slot="actions"
              @click="increaseNumber(item.id)"
              type="primary"
              shape="circle"
            >
              +
            </a-button>
            <a-button
              slot="actions"
              @click="decreaseCount(item.id)"
              type="primary"
              shape="circle"
            >
              -
            </a-button>
            <a-button
              slot="actions"
              @click="deleteProduct(item.id)"
              type="danger"
              shape="circle"
            >
              <a-icon type="delete" />
            </a-button>

            <a-list-item-meta :description="item.description">
              <h3 slot="title">{{ item.title }}</h3>
              <img slot="avatar" width="100px" alt="logo" :src="item.thumbnail" />
            </a-list-item-meta>
            <div class="list-count">{{ item.value }}</div>
          </a-list-item>
        </a-list>
      </a-col>
      <a-col
        :xl="{ span: 8 }"
        :lg="{ span: 8 }"
        :md="{ span: 12 }"
        :xs="{ span: 24 }"
      >
        <a-affix :offset-top="120">
          <a-row>
            <a-col :span="16">
              <a-alert :message="'total Bill ' + getTotalBill" type="success" />
            </a-col>
            <a-col :span="8">
              <a-button type="primary" @click="gotoCheckoutPage">
                Checkout
              </a-button></a-col
            >
          </a-row>
          <br />
          <a-table
            :columns="columns"
            :data-source="getBillBreakDown"
            :scroll="{ y: 440, x: 200 }"
          >
            <a slot="name" slot-scope="text">{{ text }}</a>
          </a-table>
        </a-affix>
      </a-col>
    </a-row>
    <!-- <div v-show="cart.length === 0">nothing to show in cart</div> -->
  </div>
</template>



<style>
.ant-list-item {
  position: relative;
  text-align: left;
}
.ant-list-item .list-count {
  position: absolute;
  top: 22px;
  right: 68px;
}
.ant-list-item-meta {
  align-items: center !important;
}
</style>
