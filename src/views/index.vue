<template>
  <navBar :class="{ show: isNavBarVisible }" id="navBar" />

  <section class="header h-lvh">
    <h1>Viureth</h1>
    <p>All In One Gaming Peripheral Online Store</p>
    <button class="btn"><arrowRightIcon id="icon" /> Shop Now</button>
  </section>

  <section class="introduction">
    <h2 class="company">Company </h2>
    <h2 class="team">Team</h2>
    <div class="card_person">
      <person class="person first">
        <template #icon>
          
        </template>
        <template #header> <h4>Founder</h4> </template>
        <template #name> <p>Lukman Danubrata</p> </template>
      </person>
      <person class="person second">
        <template #icon>
          
        </template>
        <template #header> <h4>Founder</h4> </template>
        <template #name> <p>Muhammad Rayhan Maulana</p> </template>
      </person>
    </div>
  </section>
  <fooTer id="footer" />
</template>

<script setup>
import { onMounted, onUnmounted, ref } from "vue";
import navBar from "../components/navBar.vue";
import fooTer from "../components/footer.vue";
import person from "../components/person.vue";
import arrowRightIcon from "~icons/mdi/arrow-right-circle";

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
@keyframes flow {
  0% {
    background-position: 0;
  }
  100% {
    background-position: 400%;
  }
}

#footer {
  position: relative;
}

#navBar {
  position: fixed;
  width: 100%;
  transition: all 0.5s ease-in-out;
  background-color: transparent; /* Adjust as needed */
  height: 64px; /* Adjust as needed */
  color: black;
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

.header {
  position: relative;
  background-image: url("../assets/image/background_image.jpg");
  background-size: cover;
  display: grid;
  place-content: center;
  justify-items: center;
}

.header h1 {
  font-size: 8rem;
  animation: flow 10s linear infinite ;
  background: linear-gradient(45deg, #ffbe0b, #fb5607, #ff006e, #8338ec, #3a86ff, #3a86ff, #8338ec, #ff006e, #fb5607, #ffbe0b);
  background-size: 200% ;
  -webkit-background-clip: text;
          background-clip: text;
  -webkit-text-fill-color: transparent;
  font-weight: 600;
  justify-self: center;
}

.header p {
  padding: 0 15px;
  border-radius: 15px;
  font-size: 1.5rem;
  font-weight: 400;
  color: white;
}

.header button {
  display: inline-flex;
  width: fit-content;
  margin-top: 30px;
  padding: 4px 10px;
  justify-content: center;
  align-items: center;
  gap: 10px;
  border-radius: 15px;
  outline: 2px solid white;
  font-size: 1.5rem;
  font-weight: 500;
  color: white;
  transition: all 0.2s ease-in-out;
}

.header button:hover {
  transform: scale(1.1);
  background-color: #f97316;
  outline: none;
}

.introduction {
  display: flex;
  position: relative;
  flex-direction: column;
  padding: 10px 70px;
  
  
}

.introduction h2 {
  font-size: 10rem;
  text-align: center;
  color: transparent;
  background-clip: text;
  -webkit-background-clip: text;
  transform: translate(-50%, -50%);
}

.company {
  position: absolute;
  top: 27%;
  left: 65%;
  background-image: linear-gradient(to left, #fed7aa, #f97316  );
  transform: translate(-50%, -50%);
}

.team {
  position: absolute;
  top: 70%;
  left: 30%;
  background-image: linear-gradient(to right, #fed7aa, #f97316  );
  transform: translate(-50%, -50%);
}

.person {
  display: flex;
  transform: scale(1.1);
}

.person.second {
  display: flex;
  width: 100%;
  padding-right: 90px;
  justify-content: end;
}

</style>
