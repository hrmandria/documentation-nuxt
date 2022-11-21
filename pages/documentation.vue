<script>
export default {
    data() {
      return {
        mountains: [],
        post: {}, 
        documentation : true,
        results: false,
        docs: []
      }
    },
    methods: {
      async fetch() {
        this.mountains = await fetch(
          'https://api.nuxtjs.dev/posts'
        ).then(res => res.json())
      },
      async changeContent(e) {
        this.documentation = true;
        this.results = false;
        e.stopPropagation();
        const id = parseInt(e.currentTarget.children[1].innerHTML);
        this.post = await fetch(`https://api.nuxtjs.dev/posts/${id}`).then(res => res.json());
        console.log(this.post);
      },
      async search() {
        this.results = true;
        this.documentation = false;
        const keywords = this.$refs.keywords.value;
        //dia avy eo mandefa requete fanaovana recherche amin'izay avec keywords en parametre 
      }
    },
    async mounted() {
      this.mountains = await fetch(
        'https://api.nuxtjs.dev/posts'
      ).then(res => res.json())
      this.post = await fetch('https://api.nuxtjs.dev/posts/1').then(res => res.json());
      console.log(this.post);
      this.documentation = true;
      this.results = false
    }
  }
</script>

<template>
  <div>
    <div class="navbar">
      <div class="navbar-content">
        <p>Teratany Docs</p>
        <div class="search">
          <label for="doc-search"></label>
          <input type="search" id="doc-search" name="search" ref="keywords">
          <button @click="search">Search</button>
        </div>
        <div>
          <a href="/home">Home</a>
        </div>
      </div>
    </div>
    <div class="content">
      <div class="doc-list">
        <div class="menu">
          <i>hamburger icon</i>
          <div>MENU</div>
        </div>
        <div v-for="mountain of mountains" :key="mountain.id" class="doc" @click="changeContent">
          <p class="title">{{mountain.title}}</p>
          <p class="hidden">{{mountain.id}}</p>
        </div>
      </div>
        <NuxtLink to="/create" class="nuxtlink">
          Create Documentation
        </NuxtLink>
      <div v-if="documentation" class="doc-content">
        <h1>{{post.title}}</h1>
        <p>{{post.description}}</p>
      </div>
      <div v-else>
        <p>Results</p>
        <div class="result">
          <p>Title Documentation</p>
        </div>
      </div>
    </div>
  </div>
</template>


<style>
.navbar {
  justify-content: center;
  padding-left: 4%;
  padding-right: 4%;
  margin-top:0%;
  background-color: black;
  color: white;
  height: 50px;
}

.nuxtlink {
  color: blue;
}

.navbar-content {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
}
a {
  color:white;
}
.doc-list {
  background-color: white;
  width: 200px;
  height: 590px;
  float: left;
  overflow:auto;
  justify-content:center;
  display: column;
  padding-left:2%;
  padding-right:2%;
}
.menu {
  display: flex;
  justify-content: space-between;
  margin-top: 4%;
  margin-right: 15%;
  font-weight: bold;
}
.doc {
  background-color:grey;
  width:200px;
  height: 50px;
  margin-top: 5%;
  justify-content: center;
  border-radius:10px;
  color:white;
}
.title {
  display: flex;
  justify-content: center;
  align-items: center;
  padding-top:7%;
}
.doc-content {
  padding-left: 5%;
  padding-right:5%;
  background-color:white;
  overflow:auto;
  height: 590px;
}
.hidden {
  width:200px;
  justify-content: center;
  border-radius:10px;
  margin-top: -23%;
  color:white;
  height: 100%;            
  opacity: 0.8; 
  background-color: red;
  visibility: hidden;
  z-index: 9
}
.result {
  background-color: grey;
  height: 60px;
  display: row;
  justify-content:center;
  padding-left: 10%;
  padding-right: 20%;
}

.result > p {
  padding-top: 2%;
  padding-left: 20%;
}
</style>