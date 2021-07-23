<template>
<div>
    <h1>{{produto.nome}}</h1>
    <p>{{produto.nomdescricao}}</p>
    <p>{{produto.valor}}</p>

    <button v-on:click="add()" class="btn btn-primary">Adicionar</button>
    <p>Quantidade: {{qt}}</p>
    <button v-on:click="rem()" class="btn btn-primary">retirar</button>
    <p>Valor Total: {{valortotal}}</p>
</div>
  
</template>

<script>
export default {
    layout: 'tema2',
    data() {
        return {
            nome: 'Valdir',
            qt:1,
            produto: {
                    nome:'Produto 1',
                    descricao:'Desc produdo 1',
                    valor: 20.00
                },
            valortotal: 0,
        }
    },
    methods: {
        add: function(){
            this.qt++
        },
        rem: function(){
            if(this.qt > 1){
                this.qt--
            }
            
        },
    },

    watch: {
        qt: function () {
            this.valortotal = this.qt*this.produto.valor
        }
    },


    qt: function () {

        this.valortotal = this.qt*this.produto.valor

    }

}
</script>

<style>

</style>