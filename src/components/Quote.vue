<template>
  <div class="todo col-sm-6 col-md-4 col-lg-3" @click="onDelete(quote.id)">
    <p class="text">{{quote.text}}</p>
  </div>
</template>

<script>
export default {
  props: ['quote', 'onDelete'],
}
</script>

<style scoped>
.todo {
  cursor: pointer;
}
.text {
  transition: all 0.3s;
  margin: 0;
  padding: 10px;
  box-shadow: 1px 1px 1px rgba(0, 0, 0, 0.5);
  border-radius: 5px;
  border: 1px solid #eee;
  margin: 5px;
  font-family: 'Arizonia', cursive;
  font-size: 34px;
  color: #6e6e6e;
}
.text:hover {
  box-shadow: 1px 1px 5px rgba(0, 0, 0, 0.5);
  background-color: rgba(255, 0, 0, 0.1);
}
</style>
