<template>
    <ul class="news__list">
        <li v-for="article in articles" class="news__item"> <img class="images" :src = "article.urlToImage"/> {{ article.title }}
        {{article.description}}</li>

    </ul>
</template>

<script>
export default {
 data() {
 return {
 articles: []
 }
 },
 created() {
let self = this;

 fetch('https://newsapi.org/v2/top-headlines?country=us',
{
 headers: {
    'Authorization': `Bearer ${import.meta.env.VITE_NEWSAPI_TOKEN}`

 }
})
 .then(function(response) {
 return response.json();
 })
 .then(function(data) {
 console.log(data);
 self.articles = data.articles;
 });
 }
};
</script>

<style>
  .news__item{
  display: gridbox;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  grid-gap: 20px;
  margin: 15px;

  }
 .images{
    border: 1px solid #ddd;
    border-radius: 4px;
    padding: 5px;
    width:100%;
     height: 20vw;
     object-fit: cover;
 }
</style>

