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
</style>
