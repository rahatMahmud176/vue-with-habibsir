<template>
  <div class="category-product">
      <!-- Breadcrumbs -->
		<PageBreadCrumbs/> 
		<!-- End Breadcrumbs -->
		
		<!-- Product Style -->
		<section class="product-area shop-sidebar shop section">
			<div class="container">
				<div class="row">
          <div class="col-lg-3 col-md-4 col-12">  
            <CategorySidebar/>
          </div> 
					<div class="col-lg-9 col-md-8 col-12">
						<CategoryContent/> 
					</div>
				</div>
			</div>
		</section>
		<!--/ End Product Style 1  -->
  </div>
</template>

<script>
import CategorySidebar from '@/components/Category/CategorySidebar'
import CategoryContent from '@/components/Category/CategoryContent'
import PageBreadCrumbs from '@/components/Includes/PageBreadCrumbs'
export default {
    name: "CategoryProduct",
    components:{PageBreadCrumbs, CategorySidebar, CategoryContent}, 
	

}
</script>

<style>

</style>