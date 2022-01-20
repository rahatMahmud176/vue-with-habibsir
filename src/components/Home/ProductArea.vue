<template>
  <div class="product-area">
    <!-- Start Product Area -->
    <div class="product-area section">
      <div class="container">
        <div class="row">
          <div class="col-12">
            <div class="section-title">
              <h2>Trending Item</h2>
            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-12">
            <div class="product-info">
              <div class="nav-main">
                <!-- Tab Nav -->
                <ul class="nav nav-tabs" id="myTab" role="tablist">
                  <li class="nav-item" v-for="(product, key) in products" :key="key">
                     <a class="nav-link active" v-if="key==0" data-toggle="tab" :href="'#man'+key" role="tab" >{{ product.name }}</a >
                     <a class="nav-link" v-else data-toggle="tab" :href="'#man'+key" role="tab" >{{ product.name }}</a >
                   </li> 
                    
                </ul>
                <!--/ End Tab Nav -->
              </div>
              <div class="tab-content" id="myTabContent">
                <!-- Start Single Tab -->
                <div v-for="(product, key1) in products" :key="key1" :class="['tab-pane fade show',key1==0?'active':'']" :id="'man'+key1" role="tabpanel">
                  <div class="tab-single">
                    <div class="row">
                      <div v-for="(item, key2) in product.products" :key="key2" class="col-xl-3 col-lg-4 col-md-4 col-12">
                        <div class="single-product">
                          <div class="product-img">
                            <a href="product-details.html">
                              <img
                                class="default-img"
                                :src="item.featuredImage"
                                alt="#"
                              />
                              <img
                                class="hover-img"
                                src="images/products/p2.jpg"
                                alt="#"
                              />
                            </a>
                            <div class="button-head">
                              <div class="product-action">
                                <a
                                  data-toggle="modal"
                                  data-target="#exampleModal"
                                  title="Quick View"
                                  href="#"
                                  ><i class="ti-eye"></i
                                  ><span>Quick Shop</span></a
                                >
                                <a title="Wishlist" href="#"
                                  ><i class="ti-heart"></i
                                  ><span>Add to Wishlist</span></a
                                >
                                <a title="Compare" href="#"
                                  ><i class="ti-bar-chart-alt"></i
                                  ><span>Add to Compare</span></a
                                >
                              </div>
                              <div class="product-action-2">
                                <a title="Add to cart" href="#">Add to cart</a>
                              </div>
                            </div>
                          </div>
                          <div class="product-content">
                            <h3>
                              <a href="product-details.html"
                                >{{ item.title }}</a
                              >
                            </h3>
                            <div class="product-price">
                              <span>Tk. {{ item.sellingPrice }}</span>
                            </div>
                          </div>
                        </div>
                      </div>
                       
                      
                      
                      
                    </div>
                  </div>
                </div> 
                <!--/ End Single Tab -->
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- End Product Area -->
  </div>
</template>

<script>
export default {
  name:'ProductArea',
  data(){
      return{
        products:[]
      }
  },
  created(){
      this.trandingProducts();
  },
  methods:{
        trandingProducts(){
            this.$http.get('http://localhost/admin_five/public/api/all-tranding-product').then(function(res) {
              this.products = res.body;
              console.log(res.body);
            });
        }
  },
};
</script>

<style>
</style>