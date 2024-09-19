<template>
  <div class="card_container flex w-fit">
    <div class="img">
      <slot name="icon"><img src="../assets//image/person1.jpg" alt=""></slot>
    </div>
    <div class="desc">
      <div class="header">
        <slot name="header">Default Header Content</slot>
      </div>
      <div class="content">
        <slot name="name"><h4>Lukman Danubrata</h4></slot>
        <slot name="desc"><p>SMKN 4 Bandung</p></slot>
      </div>
    </div>
  </div>
</template>

<script setup>
import personIcon from "~icons/mdi/person-circle-outline";
</script>

<style scoped>
#app {
  text-align: center;
}

.card_container {
  background-color: transparent;
  padding: 50px 20px; /* Adds some padding inside the card */
  justify-items: center;  
  gap: 10px;
  z-index: 10;
}

.img {
  position: relative;
  width: 160px;
  height: 160px;
  margin-right: 30px;
  border-radius: 100%;
  outline: 5px solid #f97316;
  outline-offset: 3px;
  overflow: hidden;
  display: grid;
  place-content: center;
  transition: all .3s ease-in-out;
}

.img:hover {
  transform: scale(1.1);
  outline-offset: 0; /* Move the outline to the edge of the image */
  outline-width: 0; /* Shrink the outline to 0 width */
  transition: all .3s ease-in-out;
}

.desc {
  display: flex;
  margin-top: 20px;
  flex-direction: column;
  align-items: start;
}

.header {
    margin-bottom: 20px;
    font-weight: bold;
    font-size: 1.8rem;
}

.content {
    font-size: 1rem;
    font-weight: 400;
}


</style>
