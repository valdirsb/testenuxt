<template>
<div>
    <h1>Pagina 1</h1>
    <p>Bem vindo {{nome}}</p>
    <button v-on:click="mudarCategoria(null)" class="btn btn-primary">All</button>
    <button v-on:click="mudarCategoria(1)" class="btn btn-primary">1</button>
    <button v-on:click="mudarCategoria(2)" class="btn btn-primary">2</button>
    <button v-on:click="mudarCategoria(3)" class="btn btn-primary">3</button>

    {{categoriaAtiva}}
    
    <div v-for="(categoria, id) in filtroCategoria?filtroCategoria:categorias" :key="id" >
        <h1>{{categoria.nome}}</h1>
        <table class="table">
            <tr>
                <td>Nome</td>
                <td>Valor</td>
                <td>imagem</td>
            </tr>
            <tr v-for="(produto, id) in categoria.produtos" :key="id">
                <td>{{produto.nome}}</td>
                <td>{{produto.valor}}</td>
                <td>{{produto.imagem}}</td>
            </tr>
        </table>
    </div>
    
</div>
  
</template>

<script>
export default {
    data() {
        return {
            nome: 'Valdir',
            categoriaAtiva: "",
            
            categorias:[
                {
                id: 1,
                nome: "Categoria 1",
                produtos: [
                    {
                    id: 1,
                    nome: "Produto 1",
                    categoria: 1,
                    valor: 15.00,
                    imagem: "image1.jpg"
                    },
                    {
                    id: 2,
                    nome: "Produto 2",
                    categoria: 1,
                    valor: 30.00,
                    imagem: "image2.jpg"
                    },
                    {
                    id: 3,
                    nome: "Produto 3",
                    categoria: 1,
                    valor: 25.00,
                    imagem: "image3.jpg"
                    },
                ]
                },
                {
                id: 2,
                nome: "Categoria 2",
                produtos: [
                    {
                    id: 4,
                    nome: "Produto 4",
                    categoria: 2,
                    valor: 15.00,
                    imagem: "image4.jpg"
                    },
                    {
                    id: 5,
                    nome: "Produto 5",
                    categoria: 2,
                    valor: 30.00,
                    imagem: "image5.jpg"
                    },
                    {
                    id: 6,
                    nome: "Produto 6",
                    categoria: 2,
                    valor: 25.00,
                    imagem: "image6.jpg"
                    },
                ]
                },
                {
                id: 3,
                nome: "Categoria 3",
                produtos: [
                    {
                    id: 7,
                    nome: "Produto 7",
                    categoria: 3,
                    valor: 15.00,
                    imagem: "image7.jpg"
                    },
                    {
                    id: 8,
                    nome: "Produto 8",
                    categoria: 3,
                    valor: 30.00,
                    imagem: "image8.jpg"
                    },
                    {
                    id: 9,
                    nome: "Produto 9",
                    categoria: 3,
                    valor: 25.00,
                    imagem: "image9.jpg"
                    },
                ]
                },

            ],
            filtroCategoria: null,
        }
    },

    watch: {
        // sempre que a Categoria Ativa, essa função será executada
        categoriaAtiva: function (n) {

            if (n==null) {
                this.filtroCategoria = null
            }else{
                this.filtroCategoria = this.categorias.filter(function (cate) {
                    return cate.id === n
                });
            }
        }
    },

    methods: {
        mudarCategoria: function(cat){
            this.categoriaAtiva = cat
        },

    }
}
</script>

<style>

</style>