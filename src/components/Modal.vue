<template>
    <div class="backdrop" @click="closeModal">
        <div class="modal" :class="{ sale: theme === 'sale'}">
            <h1>{{ header }}</h1>
            <p>{{ text }}</p>
        </div>
    </div>
</template>

<script>
export default {
    props:['header', 'text', 'theme'],
    methods:{
        closeModal(){
            this.$emit('close')
        }
    }
}
</script>
<style scoped>
.modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: rgb(193, 189, 189);
    border-radius: 10px;
}

.backdrop{
    top: 0;
    position: fixed;
    background: rbga(0,0,0,0.5);
    width: 100%;
    height: 100%;
}
h1{
    color: rgb(16, 54, 150);
}
.modal.sale{
    background-color: crimson;
    color: white;
}
.modal.sale h1{
    color: white;
}
</style>