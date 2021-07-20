(EMMET CHEATSHEET) .test#yes =>
<div class="test" id="yes"></div>

div.app =>
<div class="app"></div>

<template>
  <div id="app">
    <main>
      <div class="search-box">
        <input type="text" class="search-bar" placeholder="Search..." />
        <!-- 
(EMMET CHEATSHEET) 
.test#yes 
=>
 <div class="test" id="yes"></div>

div.app  
=>
<div class="app"></div> 
-->
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      //       We need to pull API from weather database @openweather.org

      // 1. Make an account in openweather.org
      //    https://openweathermap.org/

      // 2. Create key with VueApp as API key name
      api_key: "a33b0ed08b0cb1bc797a8395454f0096",
    };
  },
};
</script>

<style>
/* "*" className means "for all" */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "monteseratt";
}

#app {
  background-image: url("./assets/cold-bg.jpg");
  background-size: cover;
  background-position: bottom;
  transition: 0.4s;
}

main {
  min-height: 100vh;
  padding: 25px;

  background-image: linear-gradient(
    to bottom,
    rgba(0, 0, 0, 0.25),
    rgba(0, 0, 0, 0.75)
  );
}

.search-box {
  width: 100%;
  margin-bottom: 30px;
}

.search-box .search-bar {
  display: block;
  width: 100%;
  padding: 15px;

  color: #313131;
  font-size: 20px;

  appearance: none;
  border: none;
  outline: none;
  background: none;

  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 0px 16px 0px 16px;
  transition: 0.4s;
}
</style>
