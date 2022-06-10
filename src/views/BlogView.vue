<template>
  <div>
    <TitleComponent title="Página de Blog"></TitleComponent>
    <div 
        v-for="(item, index) in arrayBlog" 
        :key="index"
        class="card"
    >
        <router-link :to="`/blog/${item.id}`">
            <h3>{{ item.title }}</h3>
        </router-link>
    </div>
  </div>
</template>

<script>
import TitleComponent from '../components/TitleComponent'
export default {
    data() {
        return {
            arrayBlog: []
        }
    },
    components: { TitleComponent },
    methods: {
        async consumirApi() {
            try {
                const data = await fetch('https://jsonplaceholder.typicode.com/posts')
                const array = await data.json()
                this.arrayBlog = array;
                console.log( array );
            }catch ( err ){
                console.error(err);
            }
        }

    },
    created() {
        this.consumirApi()
    },

}
</script>

<style scoped>
.card {
    display: flex;
    flex-direction: column;
    border-radius: 6px;
    border: 1px solid #000;
    margin: 10px;
    cursor: pointe;

}
</style>