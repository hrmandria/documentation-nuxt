<script>
export default {
    data() {
      return {
        mountains: [],
        post: {}
      }
    },
    methods: {
      async fetch() {
        this.mountains = await fetch(
          'https://api.nuxtjs.dev/posts'
        ).then(res => res.json())
        alert("okay")
        alert(this.mountains)
      },
      async changeContent(e) {
        const id = parseInt(e.target.children[1].innerHTML);
        this.post = await fetch(`https://api.nuxtjs.dev/posts/${id}`).then(res => res.json());
        console.log(this.post)
      }
    },
    async mounted() {
      this.mountains = await fetch(
        'https://api.nuxtjs.dev/posts'
      ).then(res => res.json())
      this.post = await fetch('https://api.nuxtjs.dev/posts/1').then(res => res.json());
      console.log(this.post);
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
          <input type="search" id="doc-search" name="search">
          <button>Search</button>
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
          <p>{{mountain.title}}</p>
          <p class="hidden">{{mountain.id}}</p>
        </div>
      </div>
      <div class="doc-content">
        <h1>{{post.title}}</h1>
        <p>{{post.description}}</p>
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
  width:100%;
  margin-top: 5%;
  display: flex;
  justify-content: center;
  border-radius:10px;
  color:white;
  display:flex;
}
.doc-content {
  padding-left: 5%;
  padding-right:5%;
  background-color:white;
  overflow:auto;
  height: 590px;
}
.hidden {
  visibility: hidden;
}
</style>