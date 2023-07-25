<template>
    <div>
        <input type="text" v-model="cari" placeholder="Cari Data">
   
        <ul > 
            <div v-if="cariData.length === 0">
                Data Tidak Tersedia.
            </div>
            <li v-for="item in cariData" :key="item.id">
                {{ item.tittle }} - {{ item.price }}
            </li>
        </ul>
        </div>
  
</template>

<script>

export default {
    data() {
        return {
            cari: '',
            products: []
        }
    },
    created() {
        this.products = [
            { id: 1, tittle: 'Baju Anak', price: 25000 },
            { id: 2, tittle: 'Susu Anak', price: 75000 },
            { id: 3, tittle: 'Topi', price: 10000 },
            { id: 4, tittle: 'Balon', price: 1000 },
            { id: 5, tittle: 'Kinder Joy', price: 15000 }
        ]
    },
    computed: {
        cariData() {
            return this.products.filter((item) => {
                return item.tittle.match(this.cari);
            });
        }, 
         
       }
     }
    
    
</script>
