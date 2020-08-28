<template>
  <div>
    <button @click="reloadPage()" class="btn btn-dark">Random Start</button>
    <div class="row">
        <div class="col-5">
          <img style="width:60%" :src="selectedplayer.img"  alt="">
        </div>
        <div class="col-2">
          <div class="row">
            <br>
            <br>
          </div>
          <div class="row">
            <img style="width:100%" :src="versus"  alt="">
          </div>
        </div>
        <div class="col-5">
          <img style="width:60%" :src="selectedmonster"  alt="">
    </div>
    </div>
    <div class = "row">
      <div class = "col-6" >
        Player : {{selectedplayer.name}}
        <br>
         <img  v-bind:style="{width: php + 'px'}"  :src="phpbar"  alt="" height="15px">
         {{php}}
      </div>
      <div class = "col-6">
        Monster
        <br>
        <img  v-bind:style="{width: mhp + 'px'}"  :src="mhpbar"  alt="" height="15px">
        {{mhp}}
      </div>
    </div>
    <br/>
    <br/>
    <button @click="random()" v-bind:disabled = "end"  class="btn btn-dark" >Attack</button>{{space}}
    <button @click="SPrandom()" v-bind:disabled = "end" class="btn btn-dark" >SP Attack</button>
    <div id="result">
      <div v-if="mhp==0 || php==0">
        <div v-if="mhp <php">       
        Player win
    </div>
    <div v-else-if="php < mhp">
        Monster win
    </div>
    <div v-else-if="mhp==php">
        Draw
    </div>
      </div>
    </div>
    
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      end : false,
      space : "",
      phpbar : 'https://freepikpsd.com/wp-content/uploads/2019/11/fortnite-health-bar-png-Transparent-Images.png',
      mhpbar : 'https://freepikpsd.com/wp-content/uploads/2019/11/fortnite-health-bar-png-Transparent-Images.png',
      versus : 'https://www.pngmart.com/files/11/Versus-Battle-PNG-File.png',
        monster : [
            'https://64.media.tumblr.com/48485ff7398e185e4023e72eb9f55ba4/tumblr_inline_p82is4SzJd1ri065t_540.gif',
            'https://thumbs.gfycat.com/FocusedPessimisticFalcon-small.gif',
            'https://media3.giphy.com/media/fBJ4pmgGHjN1W4GBbX/source.gif',
        ],
        player : [
          {name : "ironman",img :'https://i.pinimg.com/originals/94/4f/2b/944f2b6b85eecb4e870f7f9a9cf9c793.gif'},
            {name : "nobinobi",img : 'https://sites.google.com/site/pangweb12/_/rsrc/1487331408404/-nobita/No-bita.png'},
            {name : "luffy",img : 'https://38.media.tumblr.com/c5f1df280fa287943dad93af323d37ed/tumblr_nvs2d9mdfI1s31fzzo1_500.gif'},
        ],
        selectedmonster: {name:"",img:null},
        selectedplayer : {name:"",img:null},
      ppower: "",
      mpower: "",
      php: 250,
      mhp: 250,
      term: false,
    };
  },
  methods: {
    reloadPage : function(){
    window.location.reload()
  },
    random: function () {
      this.ppower = Math.floor(Math.random() * 7 + 3);
      this.mhp = this.mhp - this.ppower;
      if(this.php<=0){
        this.php = 0
        this.end = true
      }else if(this.mhp<=0){
        this.mhp = 0
        this.end = true
      }else if(this.mhp<=0&&this.php<=0){
        this.mhp = 0
        this.php = 0
      }
      this.mpower = Math.floor(Math.random() * 7 + 3);
      this.php = this.php - this.mpower;
      if(this.php<=0){
        this.php = 0
        this.end = true
      }else if(this.mhp<=0){
        this.mhp = 0
        this.end = true
      }else if(this.mhp<=0&&this.php<=0){
        this.mhp = 0
        this.php = 0
      }
    },
    SPrandom: function () {
      this.ppower = Math.floor(Math.random() * 10 + 5);
      this.mhp = this.mhp - this.ppower;
      if(this.php<=0){
        this.php = 0
        this.end = true
      }else if(this.mhp<=0){
        this.mhp = 0
        this.end = true
      }else if(this.mhp<=0&&this.php<=0){
        this.mhp = 0
        this.php = 0
      }
      this.mpower = Math.floor(Math.random() * 10 + 5);
      this.php = this.php - this.mpower;
      if(this.php<=0){
        this.php = 0
        this.end = true
      }else if(this.mhp<=0){
        this.mhp = 0
        this.end = true
      }else if(this.mhp<=0&&this.php<=0){
        this.mhp = 0
        this.php = 0
      }
    },
    randommonster (items) {
      return items[Math.floor(Math.random()*items.length)];
    },
    randomplayer (items) {
      return items[Math.floor(Math.random()*items.length)];
    },
  },
  created() {
    this.selectedmonster = this.randommonster(this.monster)
    this.selectedplayer = this.randomplayer(this.player)
  },
  
};
</script>

<style>
#result{
  height : 50px;
  font-size : 200%;
  color :aliceblue;
}
</style>