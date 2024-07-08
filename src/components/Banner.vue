<template>
  <div class="banner">
    <a-carousel autoplay arrows>
      <div
        slot="prevArrow"
        class="custom-slick-arrow"
        style="left: 10px; z-index: 10"
      >
        <a-icon type="left-circle" />
      </div>
      <div slot="nextArrow" class="custom-slick-arrow" style="right: 10px">
        <a-icon type="right-circle" />
      </div>
      <div class="carousel-wrapper">
        <img
          src="https://themepure.net/template/vue/vue/img/bg/bg.jpg"
          width="100%"
          alt=""
        />
        <div>
          <a-row type="flex" justify="end" style="margin-right: 30px">
            <a-col :span="14">
              <h2>Furniture</h2>
              <p class="smallfont">
                The vital part of every home is furniture, and it’s the first
                thing to be considered while planning a home decor. Your home
                furniture has to be presentable and classy, as it depicts your
                values and mood. It also represents the first impression of your
                home, and we are sure that you want it to look luxurious and
                stylish. Always choose to buy furniture online in Pakistan from
                reputed online furniture and decor store.
              </p>
            </a-col>
          </a-row>
        </div>
      </div>
      <div class="carousel-wrapper">
        <img src="../assets/images/banner/c1.jpeg" width="100%" alt="" />
      </div>

      <div class="carousel-wrapper">
        <img src="../assets/images/banner/c2.jpeg" width="100%" alt="" />
      </div>
    </a-carousel>
  </div>
</template>
