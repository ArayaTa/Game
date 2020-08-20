<template>
  <div>
    <p>HP Player {{randomDamage(1,3)}}
    {{ player[randomDamage(1,3)-1].name}}
    </p>
    +รูป
    <hr />
    name = {{ aplayer.name}}
    hp={{ aplayer.hp}}
    image={{ aplayer.image}}
     <hr />
    <p>HP Monter {{randomDamage(1,3)}}
    {{ monster[randomDamage(1,3)-1].name}}
    </p>
    <button @click="start()">Start</button>
    <button @click="attack()">Attack</button>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
        aplayer:{
            name: "" , hp: 0, imag: ''
        },
      player: [
        { name: "Doraemon", hp: 150 },
        { name: "Anakin", hp: 200 },
        { name: "Skywalke", hp: 250 },
        { name: "Iron man", hp: 300 },
      ],
      monster: [
          {name: "Thanos", hp: 150}, 
          {name: "Darth vader", hp: 150}, 
          {name: " Cell", hp: 150}, 
          {name: "JaiAnt", hp: 150}, 
          ],
    };
  },
  methods: {
    randomDamage: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },
    start:function(){
        //1.random 1-3--> ชื่อ hp รูป
        this.aplayer =this.player[this.randomNo(1,3)-1]
    },
    attack:function(){
        //player-->monstor
        //player<--monster
        //player.HP<=0 ==> ?
        //monster.HP<==0 ==> ?
        //End Game
    }

  },
}
</script>