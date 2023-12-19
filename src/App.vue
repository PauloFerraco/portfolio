<template>
  <HomeView/>
</template>

<script>
import HomeView from './views/HomeView.vue'

export default {
  components: {
    HomeView
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Anton&family=Inter:wght@100;400;500;600;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100;400;500;600;700&display=swap');

body {
	font-family: 'Montserrat', sans-serif;
	background-color: var(--body);
  color: #fff;
}

* {padding: 0;margin: 0;box-sizing: border-box;}

button,textarea,li,ul,select,input,hr {border:0;list-style: none;background-color: transparent;outline: none;color: inherit;text-decoration: none;font-family: 'Montserrat', sans-serif;}
a {display: contents;text-decoration: none;color: inherit;}
input[type=radio] {display: none;}
input[type=file] {padding: 0 10px !important;font-size: 14px;}

.nobr {white-space: nowrap;text-overflow: ellipsis;overflow: hidden;}

:root {
  --body: #171721;
  --width: 1300px;
  --font: #fff;
  --blue: #2029D6;
  --color2: #4B4B6E;
}

section {
  width: var(--width);
  height: 100vh;
  padding-top: 150px;
  display: flex;
  justify-content: center;
	align-items: center;
  flex-wrap: wrap;
  
}

section .title {
  width: 100%;
  height: 30px;
  font-size: 30px;
  font-weight: 600;
  text-align: center;
  user-select: none;
  color: var(--font);
}

@media only screen and (max-width: 500px) {
  section {
    width: 100% !important;
    justify-content: center;
    flex-wrap: wrap;
    overflow: hidden;
  }
}

</style>