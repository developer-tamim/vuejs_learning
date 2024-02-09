<template>
  <div>
  <div class="backdrop" @click.self="closeModal"> 
    <div class="modal">
        <h1>{{ header }}</h1>
        <p>{{ text }}</p>
    </div>
  </div>
  </div>
</template>

<script>
export default {
  props:[
    'header',
    'text',
  ],
  methods:{
    closeModal(){
      this.$emit('close');
    }
  }
};
</script>

<style scoped>
.modal{
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: #fff;
    border-radius: 10px;
}

.backdrop{
    top: 0;
    position: fixed;
    /* background: rgba(0, 0, 0, 0.5); */
    background: rgb(0 33 3 / 50%);
    width: 100%;
    height: 100%;
}

h1{
    color: #ff0000;
    font-size: 20px;
    text-align: center;
}

</style>