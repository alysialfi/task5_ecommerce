<template>
    <div class="container">
        <div v-if="isLoading" class="product-container">
            <div class="skeleton-thumbnail"></div>
            <div class="skeleton-details">
                <div class="skeleton-details-top"></div>
                <div class="skeleton-details-bottom"></div>
            </div>
        </div>
        <div v-else class="container" :class="!isProductAvailable ? 'bg-gray' : product.data.category === 'men\'s clothing' ? 'bg-blue' : 'bg-pink'">
            <div v-if="!isProductAvailable" class="product-unavailable-container">
                <p>This product is unavailable to show</p>
                <div class="cta">
                    <button type="button" @click="getSingleProduct()" class="cta-next">Next Product</button>
                </div>
            </div>
            <div v-else class="product-container">
                <div class="product-thumbnail">
                    <img :src="product.data.image" alt="">
                </div>
                <div class="product-details">
                    <div class="top">
                        <h3 class="title">{{ product.data.title }}</h3>
                        <div class="sub-title">
                            <span>{{ product.data.category }}</span>
                            <div class="rating">
                                <span>{{ product.data.rating.rate }}/5</span>
                                <div class="rating">
                                    <span class="circle"></span>
                                    <span class="circle"></span>
                                    <span class="circle"></span>
                                    <span class="circle"></span>
                                    <span class="circle"></span>
                                </div>
                            </div>
                        </div>
                        <div class="description">
                            <p>{{ product.data.description }}</p>
                        </div>
                    </div>
                    <div class="bottom">
                        <span class="price">${{ product.data.price }}</span>
                        <div class="cta">
                            <button type="button" class="cta-buy">Buy Now</button>
                            <button type="button" @click="getSingleProduct()" class="cta-next">Next Product</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ProductDisplay',
    data() {
        return {
            
        }
    },
}
</script>

<style scoped>
    @import '../assets/style/page.css'
</style>
