<template>
  <div class="lines-view">
    <div class="selections">
      Choose a line:
      <select v-model="currentId">
	      <option
	      	v-for="l in lines"
	      	:value="l.id"
	      	:key="l.name"
      	>
	        {{ l.name }}
	      </option>
      </select>

      {{ currentId }}
    </div>
    <div class="lines-stop-list">
      <ul>
          <li
            v-for="l in stops"
            @click="setFavorite(l.station_id)"
            :style="{color: (l.is_favorite ? 'red' : 'black')}"
            :key="l.id"
          >
            {{ l.is_favorite ? `${l.name} (Favorite)` : l.name }}
          </li>
      </ul>
    </div>
  </div>
</template>

