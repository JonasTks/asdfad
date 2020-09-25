<template>
<div>
  <button class="button is-warning" @click="isActive=true">Click me</button>
  <div class="modal" :class="{'is-active' : isActive}">
  <div class="modal-background" @click="isActive=false"></div>
  <div class="modal-content">
    <div class="card">
        <img src="https://scx2.b-cdn.net/gfx/news/hires/2019/2-nature.jpg" height="1920" width="1080">
     </div>
  </div>

</div>
</template>

<script>
export default {
    data(){
        return{
            isActive: false
        }
    }

}
</script>

<style>

</style>