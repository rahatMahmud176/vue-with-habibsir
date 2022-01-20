<template>
  <div class="category-content">
       <div class="row">
							<div class="col-12">
								<!-- Shop Top -->
								<div class="shop-top">
									<div class="shop-shorter">
										<div class="single-shorter">
											<label>Show :</label>
											<select>
												<option selected="selected">09</option>
												<option>15</option>
												<option>25</option>
												<option>30</option>
											</select>
										</div>
										<div class="single-shorter">
											<label>Sort By :</label>
											<select>
												<option selected="selected">Name</option>
												<option>Price</option>
												<option>Size</option>
											</select>
										</div>
									</div>
									<ul class="view-mode">
										<li class="active"><a href="shop-grid.html"><i class="fa fa-th-large"></i></a></li>
										<li><a href="shop-list.html"><i class="fa fa-th-list"></i></a></li>
									</ul>
								</div>
								<!--/ End Shop Top -->
							</div>
						</div>
						<div class="row">
							<div class="col-lg-4 col-md-6 col-12" v-for="(product, key) in products" :key="key">
								<div class="single-product">
									<div class="product-img">
										<router-link :to="{name:'ProductDetails', params:{id:product.id} }">
											<img class="default-img" :src="product.featuredImage" alt="#">
											<img class="hover-img" :src="product.featuredImage" alt="#">
										</router-link>
										<div class="button-head">
											<div class="product-action">
												<a data-toggle="modal" data-target="#exampleModal" title="Quick View" href="#"><i class=" ti-eye"></i><span>Quick Shop</span></a>
												<a title="Wishlist" href="#"><i class=" ti-heart "></i><span>Add to Wishlist</span></a>
												<a title="Compare" href="#"><i class="ti-bar-chart-alt"></i><span>Add to Compare</span></a>
											</div>
											<div class="product-action-2">
												<a title="Add to cart" href="#">Add to cart</a>
											</div>
										</div>
									</div>
									<div class="product-content">
										<h3><a href="product-details.html">{{ product.title }}</a></h3>
										<div class="product-price">
											<span>Tk. {{ product.sellingPrice }}</span>
										</div>
									</div>
								</div>
							</div> 
						</div>
  </div>
</template>

<script>
export default {
    name:"CategoryContent",
	data(){
		return{
			id: this.$route.params.id,
			products:[]
		}
	},
	created(){
		this.categoryProduct();
	},
	methods:{
		categoryProduct(){
			this.$http.get('http://localhost/admin_five/public/api/product-by-category/'+this.id).then(function(res){
				this.products = res.body; 
			});
		}
	}

}
</script>

<style>

</style>