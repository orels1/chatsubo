<template lang="pug">
  #app
    router-view
</template>

<style>
@import url("https://fonts.googleapis.com/css?family=Inconsolata|Six+Caps");

:root {
  --dark-yellow: #ab9e85;
  --base-yellow: #b2a68e;
  --base-green: #526865;
  --dark-green: #34514d;
  --shadow: #111f21;
  --dark: #18000b;
  --red: #25080d;
  --text: #e1962e;
  --dark-text: #9a501d;
}

#app {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body,
html {
  margin: 0;
  padding: 0;
}

* {
  box-sizing: border-box;
}

body {
  display: flex;
  flex-direction: column;
  height: 100vh;
  background-color: #59625e;
  align-items: center;
}
</style>
