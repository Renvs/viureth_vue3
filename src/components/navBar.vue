<template>
  <div id="navBar" :class="{show: isNavBarVisible}" class="bg_nav flex justify-between items-center">
    <ViurethLogo />
    <div class="container_nav flex">
      <ul class="flex gap-x-5 mr-8">
        <li><a href="#">Home</a></li>
        <li><a href="#">Product</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
      <div class="container__nav flex items-center gap-x-3">
      <search class="search_nav flex px-2 py-2">
        <input type="text" placeholder="Search Product" />
        <button><SearchLogo /></button>
      </search>
      <a class="cart_nav flex items-center gap-x-1 px-2 py-1" href="#">Cart <CartLogo width="18"  /></a>
      </div>
    </div>
  </div>
</template>

<script setup>
// * Vue
import {ref, onMounted, onUnmounted} from "vue";

// * Icons
import ViurethLogo from "./../assets/Viureth_Logo.vue";
import SearchLogo from "~icons/mdi/search";
import CartLogo from "~icons/mdi/cart-outline";

// * Script
const isNavBarVisible = ref(false);

onMounted(() => {
  const handleScroll = () => {
    isNavBarVisible.value = window.scrollY > 0;
  };

  window.addEventListener("scroll", handleScroll);

  onUnmounted(() => {
    window.removeEventListener("scroll", handleScroll);
  });
});

</script>

<style scoped>
#navBar {
  position: fixed;
  width: 100%;
  transition: all 0.5s ease-in-out;
  background-color: transparent; 
  height: 64px; 
  z-index: 1000000;
  top: -100px;
}

#navBar.show {
  top: 0;
  background: rgba(51, 51, 51, 0.66);
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(10.3px);
  -webkit-backdrop-filter: blur(10.3px);
  box-shadow: -2px 1px 39px -8px rgba(0, 0, 0, 1);
  -webkit-box-shadow: -2px 1px 39px -8px rgba(0, 0, 0, 1);
  -moz-box-shadow: -2px 1px 39px -8px rgba(0, 0, 0, 1);
}


.bg_nav {
  height: 64px;
  padding: 0px 50px ;
  background: #333333;
}

.container_nav {
  display: flex;
  align-items: center;
}

.container_nav li {
    position: relative;
    transition: all .3s linear;
    font-weight: var(--font-weight);
    padding-left: 4px;
    color: var(--container-nav-color);
}

.container_nav li:hover {
    padding-right: 15px;
    transition: all .3s ease-in-out;
    background-color: rgb(249, 115, 22, 0.9);
    transform-origin: right;
}

.container_nav li::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 2px;
    background-color: var(--container-nav-color);
    bottom: 0;
    left: 0;
    transform-origin: center;
    transform: scaleX(0);
    transition: transform .3s ease-in-out;
}

.container_nav li:hover::before {
    transform-origin: center;
    transform: scaleX(1) ;
}

.container__nav {
  margin-left: 15px;
}

.search_nav {
  position: relative;
  background-color: rgb(249, 115, 22);
  color: white;
  border-radius: 13px;
  align-items: center;
  transform-origin: left;
  transition: all .5s ease-in-out;
}

.search_nav:hover {
  background-color: #ffe0c5;
  color: #ae5b0f;
}

.search_nav input {
  width: 0;
  border: none;
  outline: none;
  background-color: rgb(249, 115, 22);
  transition: 0.5s ease-in-out;
  color: white;
  font-size: small;
  font-weight: 500;
}

.search_nav input::placeholder {
  color: #f97316;
  opacity: 1;
}

.search_nav:hover input {
  width: 150px; /* Expanded width on hover */ 
  padding: 0 2px 0 10px;
  background-color: #ffe0c5;
  color: #f97316;
}

.cart_nav {
  background-color: #f97316;
  border-radius: 13px;
  font-weight: 500;
  transition: all .3s ease-in-out;
  color: white;
}

.cart_nav:hover {
  color: #ae5b0f;
  background-color: #ffe0c5;
  transform: scale(1.05) ;
  filter: drop-shadow(0 1px 1px rgb(0 0 0 / 0.05));
}

</style>

