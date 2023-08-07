<template>
    <div @click.self="closeModal" class="backdrop">
        <div class="modal" :class="{sale: theme === 'sale'}">
            <h1>Modal title </h1>
            <h3>{{header}}</h3>
            <p>{{text}}</p>
        </div>
    </div>
</template>

<script>
export default { 
    props:["header","text","theme"],
    methods:{
        closeModal(){
            this.$emit("closeModal")
        }
    }
}
</script>

<style >
.modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: #fff;
    border-radius: 10px;
}

.backdrop {
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;

}

.modal h1 {
    color: red;
}

.modal p{
    font-style: normal;
}

.modal.sale{
    background-color: crimson;
    color:#fff;
}
</style>