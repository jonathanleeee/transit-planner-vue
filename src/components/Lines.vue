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

<script>
	export default {
	  name: 'lines-view',

	  data() {
	    return {
	    	lines: Array(10).fill().map(() => ({
	    		id: ~~(Math.random() * 100),
	    		name: Math.random().toString(16).slice(2),
	    	})),
        stops: 
[
    {
        "id": 1,
        "name": "Millbrae",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 26,
        "is_transfer": 0
    },
    {
        "id": 2,
        "name": "San Francisco International Airport",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 37,
        "is_transfer": 0
    },
    {
        "id": 3,
        "name": "San Bruno",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 36,
        "is_transfer": 1
    },
    {
        "id": 4,
        "name": "South San Francisco",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 40,
        "is_transfer": 0
    },
    {
        "id": 5,
        "name": "Colma",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 11,
        "is_transfer": 0
    },
    {
        "id": 6,
        "name": "Daly City",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 13,
        "is_transfer": 0
    },
    {
        "id": 7,
        "name": "Balboa Park",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 6,
        "is_transfer": 1
    },
    {
        "id": 8,
        "name": "Glen Park",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 21,
        "is_transfer": 0
    },
    {
        "id": 9,
        "name": "24th St/Mission",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 4,
        "is_transfer": 0
    },
    {
        "id": 10,
        "name": "16th St/Mission",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 2,
        "is_transfer": 0
    },
    {
        "id": 11,
        "name": "Colma",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 11,
        "is_transfer": 0
    },
    {
        "id": 12,
        "name": "Powell St.",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 33,
        "is_transfer": 0
    },
    {
        "id": 13,
        "name": "Montgomery St.",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 27,
        "is_transfer": 0
    },
    {
        "id": 14,
        "name": "Embarcadero",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 18,
        "is_transfer": 0
    },
    {
        "id": 15,
        "name": "West Oakland",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 45,
        "is_transfer": 0
    },
    {
        "id": 16,
        "name": "12th St/Oakland City Center",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 1,
        "is_transfer": 0
    },
    {
        "id": 17,
        "name": "19th St/Oakland",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 3,
        "is_transfer": 1
    },
    {
        "id": 18,
        "name": "MacArthur",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 25,
        "is_transfer": 0
    },
    {
        "id": 19,
        "name": "Ashby",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 5,
        "is_transfer": 0
    },
    {
        "id": 20,
        "name": "Downtown Berkeley",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 14,
        "is_transfer": 0
    },
    {
        "id": 21,
        "name": "North Berkeley",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 28,
        "is_transfer": 0
    },
    {
        "id": 22,
        "name": "El Cerrito Plaza",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 17,
        "is_transfer": 0
    },
    {
        "id": 23,
        "name": "El Cerrito del Norte",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 16,
        "is_transfer": 0
    },
    {
        "id": 24,
        "name": "Richmond",
        "is_favorite": 0,
        "line_id": 1,
        "station_id": 34,
        "is_transfer": 0
    }
],
	      currentId: 1
	    };
	  },
	};
</script>
