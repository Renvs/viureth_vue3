<template>
    <navBar id="navBar"/>

    <section>
        <div class="h-[40svh]  ">
        <h1>Product</h1></div>
    </section>

    <section>
        <div class="h-screen bg-black">
        </div>
    </section>

    <fooTer id="footer"/>
</template>

<script setup>
import navBar from '../components/navBar.vue';
import fooTer from '../components/footer.vue';
</script>

<style scoped>
#navBar {
    position: fixed;
    top: 0;
    --container-nav-color: black;
}

#navBar.show {
    background: rgba(51, 51, 51, 0.8);
    --container-nav-color: white;
}

#footer {
    position: relative;
}

</style>