<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{ blue: theme === 'blue'}">
            <h1>{{ header }}</h1>
           <slot>Default content</slot>
           <div class="actions">
               <slot name="link"></slot>
           </div>
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

<style >
.modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: rgb(228, 72, 72);
    border-radius: 10px;
}
.backdrop{
    top: 0;
    position: fixed;
    background: rbga(0,0,0,0.5);
    width: 100%;
    height: 100%;
}
.modal h1{
    color: rgb(255, 255, 255);
    border: none;
    padding: 0;

}
.modal p{
    font-style: normal;
}
.modal.blue{
    background: rgb(43, 144, 222);
}
.modal  .actions{
color: white;
}
.modal .actions{
    text-align: center;
    margin: 30px 0 10px 0;
}
.modal .actions a{
    color: rgb(254, 254, 254);
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
}
.modal .actions a:hover{
    background: rgb(244, 244, 244);
    color: black;
}

</style>