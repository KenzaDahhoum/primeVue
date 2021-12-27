<template>
<div>
 <DataTable :value="products">
    <Column field="id" header="Code"></Column>
    <Column field="title" header="Name"></Column>
    <Column field="body" header="Category"></Column>
</DataTable>
   <Button>test</Button>
</div>
</template>

<script>
import ProductService from '../service/ProductService';
import Column from 'primevue/column'
import Button from 'primevue/button'
export default {
    data() {
        return {
            products: null
        }
    },
    components:{
      Column,
      Button,
      
    },
    productService: null,
    created() {
        this.productService = new ProductService();
    },
    mounted() {
        this.productService.getProducts().then(data => this.products = data);
    }
}

</script>

<style scoped>

</style>
