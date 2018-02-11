<template>
  <div class="row">
    <div class="col-sm-12">
      <h2>Quotes Added</h2>
      <div class="progress">
        <div 
          class="progress-bar" 
          role="progressbar" 
          :aria-valuenow="count" 
          aria-valuemin="0" 
          :aria-valuemax="max"
          :style="{width: ((count / max) * 100) + '%'}">
          {{count}} / {{max}}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["count", "max"]
}
</script>

<style>

</style>
