<template>
  <div>
    <img @click="ImageOnClick('https://vitejs.dev/')" class="glowImageVite" src="https://preview.redd.it/ddhpio05n9l61.png?width=410&format=png&auto=webp&s=9da01f746dbf4fac515155edf15bf9b7793ec0df"/>
    <img @click="ImageOnClick('https://vuejs.org/')" class="glowImageVue" src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/640px-Vue.js_Logo_2.svg.png"/>
  </div>
</template>

<script>
export default {
  name: "ImageShowcase",
  methods: {
    ImageOnClick(url){
      window.location.href = url
    }
  }
}
</script>

<style scoped>

.glowImageVite{
  transition: .2s;
  filter: drop-shadow(0 0 0.75rem rgb(115, 0, 255));
  height: 200px;
}
.glowImageVite:hover{
  transform: scale(1.1);
}
.glowImageVue{
  transition: .2s;
  filter: drop-shadow(0 0 0.75rem rgb(109, 178, 104));
  height: 200px;
}
.glowImageVue:hover{
  transform: scale(1.1);
}

</style>