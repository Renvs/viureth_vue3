<template>
    <div class="bg_foot w-full p-8 px-16">
        <div class="container_foot flex">
            <h1>Viureth</h1>
            <div class="container__foot">
                <ul class="flex gap-x-14">
                    <li class="head_list">Resources
                        <ol>Dropship</ol>
                        <ol>Manufacture</ol>
                    </li>
                    <li class="head_list">Company
                        <ol>About Us</ol>
                        <ol>Blog</ol>
                        <ol>Careers</ol>
                    </li>
                    <li class="head_list">Product
                        <ol>Mouse</ol>
                        <ol>Keyboard</ol>
                        <ol>Monitor</ol>
                        <ol>Gaming Chair</ol>
                    </li>
                    <li class="head_list ">Contact Us
                        <ol>Email</ol>
                        <ol>Hotmail</ol>
                    </li>
                </ul>
            </div>
        </div>
        <hr>
        <div class="container_foot_2 flex">
            <p>© 2024 Viureth™  All Rights Reserved.</p>
            <socialMedia />
        </div>
    </div>
</template>

<script setup>
import socialMedia from './icons/socialMedia.vue';
</script>

<style scoped>
* {
    color: white;
}

.bg_foot {
    position: absolute;
    bottom: 0;
    left: 0;
    background-color: #333333;
}

.container_foot {
    justify-content: space-between;
    margin-bottom: 15px;
}

.container_foot h1 {
    font-weight: 600;
    font-size: 3rem;
    background-image: linear-gradient(to left, #fed7aa, #f97316);
    color: transparent;
    background-clip: text;
    display: inline-block;
}

.container_foot_2 {
    justify-content: space-between;
    margin-top: 15px;
    opacity: 0.5;
    font-weight: 300;
}

.head_list {
    font-weight: 400;
}

.head_list ol {
    font-weight: 300;
    font-size: 0.9rem;
    opacity: 0.5;
    padding: 5px 0;
}

</style>