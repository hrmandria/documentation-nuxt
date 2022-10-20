<script setup>
const runtimeConfig = useRuntimeConfig()
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
        <div class="doc">
          <p>Documentation</p>
        </div>
      </div>
      <div class="doc-content">
        <h1>Documentation Title</h1>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        <h2>Some subtitle</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        <h2>Some subtitle</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        <h2>Some subtitle</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        <h2>Some subtitle</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        <h2>Some subtitle</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
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
}
.doc-content {
  padding-left: 5%;
  padding-right:5%;
  background-color:white;
  overflow:auto;
  height: 590px;
}
</style>