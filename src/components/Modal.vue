<template>
  <div>
    <div class="backdrop" @click.self="closeModal">
      <div class="modal" :class="{ sale: theme === 'sale' }">
        <!-- <h1>{{ header }}</h1>
        <p>{{ text }}</p> -->

        <slot></slot>
        <div class="actions">
            <slot name="link"></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["header", "text"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
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
  /* background: rgba(0, 0, 0, 0.5); */
  background: rgb(0 33 3 / 50%);
  width: 100%;
  height: 100%;
}

.modal h1 {
  color: #ff0000;
  font-size: 20px;
  text-align: center;
}
.modal p {
  font-style: normal;
}

.modal .actions{
    text-align: center;
    margin: 30px 0 10px 0;
}

.modal .actions a{
    color: #333;
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10;
}

.modal .sale{
    background: crimson;
    color: #fff;
}
.modal .sale h1{
    color: #fff;
}
.modal .sale .actions{
    color: #fff;
}
.modal .sale .actions a{
    color: #fff;
}


</style>
