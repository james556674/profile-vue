<template>
  <div class="project-page">
    <h2>My Projects</h2>
    <div class="div-line"></div>
    <div class="container">
      <div class="project-wrapper" v-for="pro in projects" :key="pro.id">
        <router-link :to="{ name: 'Project-Self', params: { id: pro.id } }">
          <div class="project-img">
            <img :src="pro.pic" />
          </div>
        </router-link>

        <div class="project-name">{{ pro.name }}</div>
        <div class="project-description">{{ pro.shortIntro }}</div>
      </div>
    </div>
  </div>
</template>

<script>
const dummyData = [
  {
    id: 1,
    name: "Simple Twitter",
    shortIntro: "簡易版推特復刻，四人協作開發，前後分離",
    longIntro:
      "四人小組開發的前後分離專案，具備新增推文、按讚推文、追蹤、公開聊天等功能。 自己在團隊中負責前端畫面切版與API串接，並使用了socket.io初步完成了公開聊天室。 ",
    tool: "Vue.js, Bootstrap, Node.js, Express.js, MySQL,Heroku ",
    demo: "https://afternoon-bayou-14704.herokuapp.com/#/signin",
    github: "https://github.com/hooty868/Twitter-API-Frontend-v1",
    pic:
      "https://camo.githubusercontent.com/cf8d1b3ed6d02d02f56c9cae1661c56a8604a85711fc38c1124d5eb77aa9099c/68747470733a2f2f6d656469612e67697068792e636f6d2f6d656469612f57486f525448637078596e795872626c63572f67697068792e676966",
  },
  {
    id: 2,
    name: "個人網站",
    shortIntro: "一個記錄著我的資訊、學習經歷、與專案的網站",
    longIntro:
      "瀏覽了許多網站後，匯集了許多想法以Vue.js框架所製作的個人網站，裡面記錄了我的相關資訊包含了我的專案作品...等等，持續優化中",
    tool: "Vue.js, FontAwesome, HTML, CSS, JS",
    demo: "",
    github: "https://github.com/james556674/My-Profile-Web-Vue",
    pic:
      "https://github.com/james556674/My-Profile-Web-Vue/blob/master/assets/projectPics/profile.png?raw=true",
  },
  {
    id: 3,
    name: "簡易記帳網站",
    shortIntro: "全端開發，以Node.js完成基本的CRUD功能",
    longIntro:
      "全端開發，以Node.js完成基本的CRUD功能，在這個網站中可以新增支出，瀏覽所有支出，瀏覽分類支出，編輯支出以及刪除支出，",
    tool: "Node.js, Express.js, Handlebars, Mongoose, MongoDB Atlas",
    demo: "https://stark-atoll-88352.herokuapp.com/",
    github: "https://github.com/james556674/expense-tracker-express",
    pic:
      "https://github.com/james556674/My-Profile-Web-Vue/blob/master/assets/projectPics/expense-tracker.png?raw=true",
  },
  {
    id: 4,
    name: "翻牌遊戲",
    shortIntro: "以Javascript為主，透過Dom實現的小遊戲",
    longIntro: "以Javascript為主，透過Dom實現的翻牌記憶小遊戲．",
    tool: "HTML, CSS, JavaScript",
    demo: "https://codepen.io/James556674/pen/BaKxgaj",
    pic:
      "https://raw.githubusercontent.com/james556674/My-Profile-Web-Vue/master/assets/projectPics/card-flip-game.png",
  },
];
export default {
  data() {
    return {
      projects: [],
    };
  },
  created() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      this.projects = dummyData;
    },
  },
};
</script>

<style scoped>
.project-page {
  margin: auto;
  min-width: 300px;
}
.container {
  margin: auto;
  width: 80%;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(360px, 1fr));
  justify-items: center;
}

.project-wrapper {
  width: 300px;
  margin-top: 2rem;
}

.project-img {
  width: 350px;
  height: 200px;
  background: grey;
  cursor: pointer;
}

.project-img:hover {
  transform: translate(-1px, -5px);
  transition: all 0.2s ease-out;
}
.project-img img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  box-shadow: 0px 4px 8px rgba(38, 38, 38, 0.2);
}

.project-name {
  color: grey;
  margin-top: 1rem;
  text-align: left;
}

.project-description {
  color: black;
  text-align: left;
  font-size: 14px;
}
</style>