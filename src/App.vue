<template>
<section>
<div class="row">
  <div class="col-6">
          <p v-if="selectedPlayer"><img style="height:500px" :src="selectedPlayer" alt=""></p>
  </div>
  <div class="col-6">
          <p v-if="selectedMonster"><img style=" height:500px" :src="selectedMonster" alt=""></p>
  </div>
</div>
<div>
    <button @click="random()"> Attack </button>
    <button @click="Srandom()"> Spacial Attack </button>
  </div>
</section>

  
</template>

<script>
export default {
data () {
    return {
      player: [
        'https://i.pinimg.com/originals/78/ac/aa/78acaad3c2890c0d47f94ec7b3cce9fb.jpg',
        'https://vignette.wikia.nocookie.net/starwars/images/6/6f/Anakin_Skywalker_RotS.png/revision/latest?cb=20130621175844',
        'https://vignette.wikia.nocookie.net/doraemonthailand/images/c/c6/180.PNG/revision/latest/top-crop/width/360/height/450?cb=20151004142603&path-prefix=th'
        
      ],
      monster:[
        'https://www.hobbymodel.net/web/board/2017/teeDSVIMPCDCA5520175550.jpg',
        'https://vignette.wikia.nocookie.net/dragonball/images/b/b4/Cell_DBZ_Ep_177_001.png/revision/latest?cb=20170921030318',
        'https://i.pinimg.com/236x/23/f9/9d/23f99d9d7897f3d1966fd4e228927a2f.jpg',
      ],
      selectedPlayer: '' ,
      selectedMonster: ''
    }
  },
  random: function () {
      this.ppower = Math.floor(Math.random() * 7 + 3,);
      this.mhp = this.mhp - this.ppower;
      this.mpower = Math.floor(Math.random() * 7 + 3);
      this.php = this.php - this.mpower;
    },
    Srandom: function () {
      this.ppower = Math.floor(Math.random() * 10 + 5);
      this.mhp = this.mhp - this.ppower;
      this.mpower = Math.floor(Math.random() * 10 + 5);
      this.php = this.php - this.mpower;
    },
  created () {
    const p1 = Math.floor(Math.random() * this.player.length)
    this.selectedPlayer = this.player[p1]
    const p2 = Math.floor(Math.random() * this.monster.length)
    this.selectedMonster = this.monster[p2]
  }
}
</script>

<style>
  
</style>