<template>
    <div>
        <TitleComponent title="Ruta con parámetros"></TitleComponent>
        <h2> {{ articulo.title }}</h2>
        <p>{{ articulo.body }}</p>
    </div>
</template>

<script>
import TitleComponent from '../components/TitleComponent'
export default {
    data() {
        return {
            articulo: {
            }
        }
    },
    components: { TitleComponent },
    methods: {
        async consumirApi() {
            try {
                const param = this.$route.params.id;
                const data = await fetch(`https://jsonplaceholder.typicode.com/posts/${param}`)
                const objeto = await data.json()
                console.log( objeto)
                this.articulo =  objeto;
            }catch ( err ){
                console.error(err);
            }
        }
    },
    created() {
        this.consumirApi();
    }

}
</script>

<style>

</style>