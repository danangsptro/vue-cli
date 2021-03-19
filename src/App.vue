<template>

<div id="app">

  <Header v-on:ganti-hero="klik()"></Header>
  
  <main>
      <p>Hero Hero Terbaik Minggu ini</p>

        <article v-if="!selectedHero">
          <Hero v-for="(item, index) of hero" :key="item.id" :hero="item" :index="index"></Hero>
        </article>
        <article v-else>
          <Hero v-bind:hero="selectedHero" :index="0"></Hero>
        </article>
      
  </main>

  <Footer></Footer>

</div>
</template>


<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Hero from './components/Hero.vue'

export default {
  components: {
    Header,
    Footer,
    Hero
  },
  name: 'App',
  data: function () {
    return{
      hero: [
        {
          id: 1,
          nama: 'Roger',
          type: 'Fighter',
          gambar: 'roger.jpg'
        },
        {
          id: 2,
          nama: 'zilong',
          type: 'fighter',
          gambar: 'zilong.jpg'
        },
        {
          id: 3,
          nama: 'Akai',
          type: 'tank',
          gambar: 'akai.jpg'
        },
        {
          id: 4,
          nama: 'nana',
          type: 'support',
          gambar: 'nana.png'
        },
        {
          id: 5,
          nama: 'layla',
          type: 'mm',
          gambar: 'layla.jpg'
        },
        {
          id: 6,
          nama: 'bruno',
          type: 'mm',
          gambar: 'bruno.jpg'
        },
        {
          id: 7,
          nama: 'hilda',
          type: 'tank',
          gambar: 'hilda.jpg'
        },
      ],
      selectedHero: ''
    }
  },
  methods: {
    klik: function(){
      this.selectedHero = this.randomHero()
    },
    randomHero(){
      return this.hero[Math.floor(Math.random() * this.hero.length)]
    }
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
main img{
  width: 80px;
  border: 1px solid #ccc;
}
article{
  display: flex;
  flex: wrap;
  justify-content: center;
}
</style>
