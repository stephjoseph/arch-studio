<script>
  import { register } from "swiper/element/bundle";

  register();

  let activeIndex = 0;

  const onProgress = (e) => {
    const [swiper, progress] = e.detail;
    // console.log(progress);
  };
  const onSlideChange = (e) => {
    console.log("slide changed");
    activeIndex = e.detail[0].activeIndex;
  };
</script>

<div class="home-hero">
  <swiper-container
    slides-per-view={1}
    autoplay={{ delay: 5000, disableOnInteraction: false }}
    on:swiperprogress={onProgress}
    on:swiperslidechange={onSlideChange}
  >
    <swiper-slide>Slide 1</swiper-slide>
    <swiper-slide>Slide 2</swiper-slide>
    <swiper-slide>Slide 3</swiper-slide>
    <swiper-slide>Slide 4</swiper-slide>
  </swiper-container>
</div>

<style lang="scss">
  .home-hero {
    width: 100vw;
    height: 560px;
  }
</style>
