<template>
  <div class="col-md-8 col-md-offset-2 text-center">
    <h5>Enter Quote</h5>
    <textarea class="form-control" rows="3" v-model="text"></textarea>
    <br />
    <button class="btn btn-primary" @click="handleSubmit">Submit</button>
  </div>  
</template>

<script>
export default {
  props: {
    onSubmit: {
      type: Function,
      required: true,
    },
  },
  data() {
    return {
      text: '',
    }
  },
  methods: {
    handleSubmit() {
      this.onSubmit(this.text)
      this.text = ''
    },
  },
}
</script>
  
<style>

</style>
