<template>
    <div class="backdrop" @click.self="close">
        <div class="modal" :class="{sale: theme === 'sale'}">
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default{
    props: ['theme'],
    methods: {
        close() {
            this.$emit('close')
        }
    },
    data() {
        return{
            
        }
    }
}
</script>

<style>
.modal{
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
    }
.backdrop{
    top: 0;
    position: fixed;
    background-color: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
}
h1{
    color: #03cfb4;
    border: none;
    padding:0;
}

.modal.sale{
    background: crimson;
    color: white;
}

.modal.sale h1{
    color:white;
}
.modal .actions{
    text-align: center;
    margin: 30px 0 10px 0 ;
}
.modal .actions a{
    color: #333;
    padding: 8px;
    border: solid 1px #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
}
.modal .sale .actions{
    color: white;
}

.modal .sale .actions a{
    color: white;
}
</style>