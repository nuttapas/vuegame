<template>
    <div>
        <p>{{choseName}}</p>
  <button @click="piker">Choose!</button>
    </div>
</template>

<script>
export default {
    data : function(){
        return{
            player: [
                {name: 'ironman', hp: 200, img:'img/ironman.png'},
                {name: 'doremon', hp: 180, img:'img/doremon.png'},
                {name: 'anakin', hp: 190, img:'img/anakin.png'}
            ],
            monster: [
                {name: 'thanos', hp: 230, img:'img/thanos.png'},
                {name: 'darthvader', hp: 220, img:'img/darthvader.png'},
                {name: 'cell', hp: 210, img:'img/cell.png'},
            ],
            chosenName: ''
    }
},
methods : {
    randomdamage : function(min,max){
      return Math.max(Math.floor(Math.random() * max) + 1,min)
    },
  
    picker: function(){
      var chosenNumber = Math.floor(Math.random() * this.player.length);
      this.chosenName = this.player[chosenNumber];
    },
    randommonster : function(){
      return Math.floor(Math.random() * this.monster.length)
    },
    hpplayer : function(){
        return (Math.floor * this.randomplayer[1]) - this.randomdamage
    },
    hpmonster : function(){
        return (Math.floor * this.randommonster[1]) - this.randomdamage
    },
    },
    
}
</script>

<style>
    
</style>