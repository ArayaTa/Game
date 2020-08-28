<template>
  <div>
    <div class="row">
      <div class="col-6">
        <p>🔥 ℙ𝕃𝔸𝕐𝔼ℝ 🔥</p>
        {{aPlayer.name}}
        <br />
        <img :src="hp1" height="50px" />
        🄷🄿 {{aPlayer.hp}}
      </div>
      <div class="col-6">
        <p>👹 𝕄𝕆ℕ𝕊𝕋𝔼ℝ 👹</p>
        {{aMonster.name}}
        <br />
        <img :src="hp2" height="50px" />
        🄷🄿 {{aMonster.hp}}
      </div>
    </div>
    <div class="row">
      <div class="col-5">
        <br />
        <br />
        <div style="position: absolute; z-index: 2;">
          <img style="width:150%" :src="aPlayer.img" />
        </div>
      </div>
      <div class="col">
        <br />
        <div v-if="aMonster.hp <=0 ">
          𝓨𝓞𝓤 𝓦𝓘𝓝
          <br />
          <br />
          <img
            src="https://media0.giphy.com/media/j60ApxGWly8qG53DHo/giphy.gif"
            width="20%"
          />
        </div>
        <div v-else-if="aPlayer.hp <= 0 ">
          𝓨𝓞𝓤 𝓛𝓞𝓢𝓔
          <br />
          <br />
          <img
            src="https://i.pinimg.com/originals/66/65/1d/66651d8d03f2fac250a707466296472c.gif"
            width="20%"
          />
        </div>
        <br />
        <div class="row">
          <img
            src="https://thumbs.gfycat.com/UnfoldedWelllitAdeliepenguin-size_restricted.gif"
            width="30%"
          />
          <!-- Vs-->
          <div class="col-6">
           <div style="position: absolute; z-index: 4;">
             <img style="width:150%" :src="aMonster.img" />
             </div>
        </div>
        </div>
      </div>
    </div>
    <br />
    <br />
    <br />
    <br />
    <div class="d-flex justify-content-center">
      <div class="but">
        <div class="col-15">
          <button @click="start()" class="btn btn-light ml-2"> ꜱᴛᴀʀᴛ </button>
          <button v-bind:disabled="end" @click="attack()" class="btn btn-light ml-2"> ᴀᴛᴛᴀᴄᴋ </button>
          <button v-bind:disabled="end" @click="specialattack()" class="btn btn-light ml-2"> ꜱᴘᴇᴄɪᴀʟ ᴀᴛᴛᴀᴄᴋ </button>
          <button @click="reset()" class="btn btn-light ml-2"> ʀᴇꜱᴇᴛ </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      win:
        "https://thumbs.gfycat.com/TalkativeSkinnyFinwhale-size_restricted.gif",
      playmax:
        "https://2.bp.blogspot.com/-Y4D3zyo2ETY/Wt-LXPf4WxI/AAAAAAAABWQ/TdYzOr3fdioqDgyo6lq-uXe7wfuhgP1swCLcBGAs/s1600/Thanos%2B10.gif",
      monsmax:
        "https://thumbs.gfycat.com/DistinctHelpfulGrayreefshark-max-1mb.gif",
      hp1: "https://media.moddb.com/images/games/1/53/52055/Health_bar_1.gif", // พลังชีวิต
      hp2: "https://media.moddb.com/images/games/1/53/52055/Health_bar_1.gif",
      end: false,
      aPlayer: { name: "", hp: 1, img: "", hp1: "" },
      // ชื่อ player[1].name  randomเอา
      player: [
        {
          name: "ⒽⓊⓁⓀ",
          hp: 370,
          img:
            "https://thumbs.gfycat.com/PrestigiousHonoredIndri-size_restricted.gif",
          width: "200%",
        },
        {
          name: "ⒾⓇⓄⓃ ⓂⒶⓃ",
          hp: 450,
          img:
            "https://66.media.tumblr.com/97279c37264ccdf40302a12ff33958b3/tumblr_mgrbnb2nYr1rfjowdo1_r1_500.gif",
          width: "200%",
        },
        {
          name: "ⒶⓃⓉⓂⒶⓃ",
          hp: 200,
          img: "https://i.imgur.com/3ZBC5Hc.gif",
          width: "300%",
        },
        {
          name: "ⓈⓅⒾⒹⒺⓇ ⓂⒶⓃ",
          hp: 310,
          img:
            "https://lh3.googleusercontent.com/proxy/sT_ERGckGznR5UPTt6gWefEPLzWpYiYOiXut7H455oyAJJueWxKfFd9cQWn6YxYT84xNBrv8wCktylX491eDtBW5",
          width: "300%",
        },
        {
          name: "ⒸⒶⓅⓉⒶⒾⓃ ⒶⓂⒺⓇⒾⒸⒶ",
          hp: 340,
          img:
            "https://i.kym-cdn.com/photos/images/original/000/709/076/eb3.gif",
          width: "300%",
        },
      ],

      aMonster: { name: "", hp: 1, img: "", hp2: "" },
      monster: [
        {
          name: "ⓉⒽⒶⓃⓄⓈ",
          hp: 460,
          img:
            "https://thumbs.gfycat.com/BrokenSerpentineAfricanbushviper-size_restricted.gif",
          width: "200%",
        },
        {
          name: "ⓋⒺⓃⓄⓂ",
          hp: 350,
          img:
            "https://i.pinimg.com/originals/bf/09/04/bf090415e0b2d7fbc25e1cb61e155e82.gif",
          width: "100%",
        },
        {
          name: "ⓋⒺⓃⓄⓂ ⓂⒶⓍ",
          hp: 300,
          img: "https://thumbs.gfycat.com/KlutzyRashDromaeosaur-max-1mb.gif",
          width: "200%",
        },
        {
          name: "ⓋⒺⓃⓄⓂ ⓌⒾⓀⒾⒶ",
          hp: 230,
          img:
            "https://vignette.wikia.nocookie.net/mugen/images/c/c4/TOPSCNightmare1.gif/revision/latest/top-crop/width/220/height/220?cb=20150320130250",
          width: "200%",
        },
        {
          name: "ⒷⒶⓉⓂⒶⓃ",
          hp: 200,
          img: "https://giffiles.alphacoders.com/728/7283.gif",
          width: "200%",
        },
      ],
    };
  },
  methods: {
    random: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },

    start: function () {
      //1.random player 1-3  ชื่อ hp รูป
      this.aPlayer = this.player[this.random(1, 5) - 1];
      this.aMonster = this.monster[this.random(1, 5) - 1];
    },
    attack: function () {
      this.playmax = Math.floor(Math.random() * 10 + 5);
      this.aPlayer.hp = this.aPlayer.hp - this.playmax;
      this.monsmax = Math.floor(Math.random() * 10 + 5);
      this.aMonster.hp = this.aMonster.hp - this.monsmax;
      if (this.aPlayer.hp <= 0) {
        this.aPlayer.hp <= 0;
        this.end = true;
      } else if (this.aMonster.hp <= 0) {
        this.aMonster.hp <= 0;
        this.end = true;
      }
    },
    specialattack: function () {
      this.playmax = Math.floor(Math.random() * 15 + 5);
      this.aPlayer.hp = this.aPlayer.hp - this.playmax;
      this.monsmax = Math.floor(Math.random() * 15 + 5);
      this.aMonster.hp = this.aMonster.hp - this.monsmax;
      if (this.aPlayer.hp <= 0) {
        this.aPlayer.hp = 0;
        this.end = true;
      } else if (this.aMonster.hp <= 0) {
        this.aMonster.hp = 0;
        this.end = true;
      }
    },
    reset: function () {
      window.location.reload();
    },
  },
};
</script>

<style >
div {
  font-size: 20px;
  color: rgb(253, 253, 253);
  margin: 50;
  padding: 50;
}
.but {
  position: fixed;
  bottom: 55px;
  color: rgb(141, 20, 20);
}
</style>