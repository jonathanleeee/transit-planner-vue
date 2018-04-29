<template>
  <div id="app">
    <div class="panel">
      <h1>Transit Planner</h1>
      <nav class="nav">
        <span 
          :class="['nav-item', {
            selected: (view === 'lines'),
            unselected: (view !== 'lines'),
          }]"
          @click="changeView('lines')"
        >
          Lines
        </span>
        <span 
          :class="['nav-item', {
            selected: view === 'planner',
            unselected: view !== 'planner',
          }]"
          @click="changeView('planner')"
        >
          Trip Planner
        </span>
      </nav>
      <div class="main-view">
        <lines v-if="view === 'lines'" />
        <trip-planner v-else />
      </div>
    </div>
    <div class="map-panel">
      <img src="./assets/bart-system-map.png"/>
    </div>
  </div>
</template>

<script>
import Lines from './components/Lines.vue'
import TripPlanner from './components/TripPlanner.vue'

export default {
  name: 'app',

  components: {
    Lines,
    TripPlanner
  },

  data() {
    return {
      view: 'lines',
    };
  },

  methods: {
    changeView(view) {
      this.view = view;
    },
  },
};
</script>

<style>
:root {
  --darktext: #333333;
  --lighttext: #FEFEFE;
}

html, body {
  margin: 0;
  padding: 0;
  font-family: Helvetica;
  color: #333333;
  background: #FEFEFE;
}

p {
  margin: 0;
  padding: 0;
}

nav {
  padding: 5px;
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  border-bottom: 1px solid lightgray;
}

.nav-item {
  border: 1px solid darkgray;
  padding: 5px;
  background: lightgray;
  margin: 5px;
  width: 50%;
  text-align: center;
}

.nav-item:hover {
  cursor: pointer;
  background: darkgray;
}

.selected {
  font-weight: bolder;
}

.unselected {
  font-weight: normal;
  background: #e3e3e3;
}

.panel {
  height: 100vh;
  width: 400px;
  float: left;
  border-right: 1px solid lightgray;
}

.panel h1 {
  padding-left: 15px;
}

.selections {
  padding: 10px;
}

.selections select {
  font-size: 1em;
  margin: 5px;
}

.selections button {
  font-size: 1em;
  margin: 5px;
  width: 100%;
}

.map-panel {
  width: 100%;
}

.map-panel img {
  width: 800px;
  height: 800px;
}

.shadow {
  box-shadow: 0px 0px 5px 1px lightgrey;
}

.directions {
  margin: 15px;
  border: 1px solid lightgray;
  border-radius: 5px;
}

.directions-step:hover {
  box-shadow: 0px 0px 5px 1px lightgrey;
}

.directions-summary {
  min-height: 50px;
  padding: 5px;
  border-bottom: 1px solid lightgray;
}

.directions-line-header {
  background: #4c4c4c;
  color: var(--lighttext);
  height: 50px;
  line-height: 25px;
  padding: 5px;
}

.directions-list-container {
  padding: 5px;
}

.line-name {
  font-size: 1.4em;
  font-weight: bolder;
  border-top: 1px solid white;
  padding-top: 3px;
}

.line-direction {
  font-size: .9em;
  font-style: italic;
  color: #d6d6d6;
}

.directions-summary > p {
  line-height: 25px;
}

.directions-step {
  min-height: 50px;
  margin: 15px;
  border: 1px solid lightgray;
}

.orange-line {
  background-color: #ff9933;
}

.blue-line {
  background-color: #0099cc;
}

.red-line {
  background-color: #ed1d24;
}

.green-line {
  background-color: #4cb848;
}

.yellow-line {
  background-color: #ffe800;
}

.line-circle {
  height: 40px;
  width: 40px;
  border-radius: 40px;
  margin: 5px 15px 5px 5px;
  float: left;
}
</style>
