<template>
  <ul>
      <li>
            <img :src='gambar'>
            <p>{{index+1}} - {{hero.nama}}</p>
            <p>Jenis Hero : <u>{{hero.type}}</u></p>
      </li>
  </ul>
</template>

<script >
    export default {
        props: ['hero', 'index'],
        computed: {
            gambar: function(){
                return require('../assets/hero/' + this.hero.gambar)
            }
        }
    }
</script>    

<style scoped>
p{
    color: salmon;
}
</style>