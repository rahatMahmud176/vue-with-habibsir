<template>
  <div class="product-basic-info"> 
<div class="product-des">
    <!-- Description -->
    <div class="short"> 
        <h4>{{ product.title }}</h4>
        <div class="rating-main">
            <ul class="rating">
                <li><i class="fa fa-star"></i></li>
                <li><i class="fa fa-star"></i></li>
                <li><i class="fa fa-star"></i></li>
                <li><i class="fa fa-star-half-o"></i></li>
                <li class="dark"><i class="fa fa-star-o"></i></li>
            </ul>
            <a href="#" class="total-review">(102) Review</a>
        </div>
        <p class="price"><span class="discount">Tk.{{ product.sellingPrice}}</span><s>tk.{{ product.regularPrice}}</s> </p>
        <p class="description">{{ product.shortDescription }}</p>
    </div>
    <!--/ End Description -->
    <!-- Color -->
    <div class="color">
        <h4>Available Options</h4>
        <p>Color</p>
       <ul> 
            <div class="form-check" v-for="(color, key) in product.colorTitle" :key="key">
            <input v-if="key==0" checked class="form-check-input" type="radio" name="color" :id="'color'+key" value="">
            <input v-else class="form-check-input" type="radio" name="color" :id="'color'+key" value="">
            <label class="form-check-label" :for="'color'+key">
               {{ color }}
            </label>
            </div> 
            <!-- <li ><a href="#" class="one">{{ size }}</a></li>  -->
        </ul>
    </div>
    <!--/ End Color -->
    <!-- Size -->
    <div class="size">
        <h4>Size</h4>
        <ul> 
            <div class="form-check" v-for="(size, key) in product.sizesTitle" :key="key">
            <input v-if="key==0" checked class="form-check-input" type="radio"  name="size" :id="'size'+key" value="">
            <input v-else class="form-check-input" type="radio"  name="size" :id="'size'+key" value="">
            <label class="form-check-label" :for="'size'+key">
               {{ size }}
            </label>
            </div> 
            <!-- <li ><a href="#" class="one">{{ size }}</a></li>  -->
        </ul>
    </div>
    <!--/ End Size -->
    <!-- Product Buy -->
    <div class="product-buy">
        <div class="quantity">
            <h6>Quantity :</h6>
            <!-- Input Order -->
            <div class="input-group">
                <div class="button minus">
                    <button type="button" class="btn btn-primary btn-number" disabled="disabled" data-type="minus" data-field="quant[1]">
                        <i class="ti-minus"></i>
                    </button>
                </div>
                <input type="text" name="quant[1]" class="input-number"  data-min="1" data-max="1000" value="1">
                <div class="button plus">
                    <button type="button" class="btn btn-primary btn-number" data-type="plus" data-field="quant[1]">
                        <i class="ti-plus"></i>
                    </button>
                </div>
            </div>
            <!--/ End Input Order -->
        </div>
        <div class="add-to-cart">
            <a href="#" :class="['btn',product.stockStatus=='Stock Out'?'disabled text-danger':'']">Add to cart</a>
            <a href="#" class="btn min"><i class="ti-heart"></i></a>
            <a href="#" class="btn min"><i class="fa fa-compress"></i></a>
        </div>
        <p class="cat">Category :<a href="#">{{ product.category }}</a></p>
        <p class="availability">Availability : {{ product.stockStatus }}</p>
    </div>
    <!--/ End Product Buy -->
</div>
</div>
 
</template>

<script>
export default {
    name:"ProductBasicInfo",
    data(){
        return {
            id: this.$route.params.id,
            product: '', 
        }
    },
    methods:{
        getProductBasicInfo(){
            this.$http.get('http://localhost/admin_five/public/api/get-product-basic-info-for-details-page/'+this.id).then(function(res){
                this.product = res.body;
            })
        }
    },
    mounted(){
       
    },
    created(){
        this.getProductBasicInfo();
    }

}
</script>

<style>

</style>