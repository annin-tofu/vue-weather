<template>
  <div id="app">
    <main>
      <div class="search-box">
        <input
          type="text"
          class="search-bar"
          placeholder="Search..."
          v-model="query"
          @keypress="fetchWeather"
        />
      </div>

      <div class="weather-wrap">
        <div class="location-box">
          <div class="location">
            {{ weather.name }}, {{ weather.sys.country }}
          </div>
          <div class="date">Wednesday July 21 2020</div>
        </div>

        <div class="weather-box">
          <div class="temp">30°C</div>
          <div class="weather">Sunny</div>
        </div>
      </div>
    </main>
  </div>
</template>
<!-- 
(EMMET CHEATSHEET) 
.test#yes 
=>
 <div class="test" id="yes"></div>

div.app  
=>
<div class="app"></div> 
-->

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
      url_base: "https://openweathermap.org/data/2.5/",
      query: "",
      // make "weather" a data object
      weather: {},
    };
  },
  method: {
    fetchWeather(e) {
      if (e.key == "Enter") {
        fetch(
          `${this.api_base}weather?q=${this.query}%units=metric&APPID=${this.api_key}`
        )
          .then((res) => {
            return res.json();
          })
          .then(this.setResults);
      }
    },
    setResults(results) {
      this.weather = results;
    },
  },
};
</script>

<style>
/* add a Google Font to a VueJS */
/* https://stackoverflow.com/questions/51516084/how-do-i-add-a-google-font-to-a-vuejs-component */
@import url("https://fonts.googleapis.com/css?family=Montserrat");

/* "*" className means "for all" */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "Montserrat", sans-serif;
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

  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 0px 16px 0px 16px;
  transition: 0.4s;
}

.search-box .search-bar:focus {
  box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.75);
  border-radius: 16px 0px 16px 0px;
}

.location-box .location {
  color: #fff;
  font-size: 32px;
  font-weight: 500;
  text-align: center;
  text-shadow: 1px 3px rgba(0, 0, 0, 0.25);
}

.location-box .date {
  color: #fff;
  font-size: 20px;
  font-weight: 300;
  font-style: italic;
  text-align: center;
}

.weather-box {
  text-align: center;
}

.weather-box .temp {
  display: inline-block;
  padding: 10px 25px;
  color: #fff;
  font-size: 102px;
  font-weight: 900;

  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.25);
  border-radius: 16px;
  margin: 30px 0px;

  box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}

.weather-box .weather {
  color: #fff;
  font-size: 48px;
  font-weight: 700;
  font-style: italic;
  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
</style>
