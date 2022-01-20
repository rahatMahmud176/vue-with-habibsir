<template>
  <div class="home">
    <Slider />
    <SmallBaner />
    <ProductArea />
    <MidiumBanner />
    <MostPopular />
    <ShopHomeList />
    <CownDown />
    <ShopBlog />
    <ShopService />
    <Newsletter />
    <Modal />
  </div>
</template>

<script>
// @ is an alias to /src
import Slider from "@/components/Home/Slider";
import SmallBaner from "@/components/Home/SmallBanner";
import ProductArea from "@/components/Home/ProductArea";
import MidiumBanner from "@/components/Home/MidiumBanner";
import MostPopular from "@/components/Home/MostPopular";
import ShopHomeList from "@/components/Home/ShopHomeList";
import CownDown from "@/components/Home/CownDown";
import ShopBlog from "@/components/Home/ShopBlog";
import ShopService from "@/components/Home/ShopService";
import Newsletter from "@/components/Home/Newsletter";
import Modal from "@/components/Home/Modal";
export default {
  name: "Home",
  components: {
    Slider,
    SmallBaner,
    ProductArea,
    MidiumBanner,
    MostPopular,
    ShopHomeList,
    CownDown,
    ShopBlog,
    ShopService,
    Newsletter,
    Modal,
  },
};
</script>
