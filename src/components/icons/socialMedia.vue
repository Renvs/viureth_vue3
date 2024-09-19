<template>
  <div class="flex gap-x-1">
    <ol>
      <InstagramIcon width="32" height="32" />
    </ol>
    <ol>
      <LinkedinIcon width="32" height="32" />
    </ol>
    <ol>
      <GithubIcon width="32" height="32" />
    </ol>
    <ol><FacebookIcon width="32" height="32" /></ol>
  </div>
</template>

<script setup>
import InstagramIcon from '~icons/mdi/instagram';
import LinkedinIcon from '~icons/mdi/linkedin';
import GithubIcon from '~icons/mdi/github';
import FacebookIcon from '~icons/mdi/facebook';

</script>

<style scoped>
.head_list ol {
    font-weight: 300;
    font-size: 0.9rem;
    opacity: 0.5;
    padding: 8px 0;
}

</style>
