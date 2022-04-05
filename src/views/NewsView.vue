<template>
    <div class="news container">
    <h2>News</h2>
    <NewsList></NewsList>
    </div>
</template>

<script>
import NewsList from '@/components/NewsList.vue'
export default {
  components: { NewsList },
    data() {
        return {};
    },
};
components: { NewsList }
</script>

<style></style>