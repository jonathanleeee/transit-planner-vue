<template>
    <div class="trip-planner-view">
		  <div class="selections">
		    Start:
		    <select>
		        <option>Hardcoded Station Name A</option>
		        <option>Hardcoded Station Name B</option>
		        <option>Hardcoded Station Name C</option>
		        <option>Hardcoded Station Name D</option>
		        <option>Hardcoded Station Name E</option>
		        <option>Hardcoded Station Name F</option>
		    </select>

		    <br /> End:
		    <select>
		        <option>Hardcoded Station Name A</option>
		        <option>Hardcoded Station Name B</option>
		        <option>Hardcoded Station Name C</option>
		        <option>Hardcoded Station Name D</option>
		        <option>Hardcoded Station Name E</option>
		        <option>Hardcoded Station Name F</option>
		    </select>

		    <br />

		    <button>Go!</button>
			</div>
			<div class="directions">
			    <div class="directions-summary">
			        <p class="line-name">Station A to Station E</p>
			        <p>31 minutes (arrive at 5:51pm)</p>
			    </div>

			    <div class="directions-step">
			        <div class="directions-line-header">
			            <p class="line-name">Start at Station A</p>
			        </div>
			    </div>

			    <div class="directions-step">
			        <div class="directions-line-header">
			            <div class="line-circle" :style="{backgroundColor: '#ed1d24'}"></div>
			            <p class="line-name">Red Line</p>
			            <p class="line-direction">towards Station C</p>
			        </div>
			        <ul>
			            <li> Station A </li>
			            <li> Station B </li>
			            <li> Station C </li>
			        </ul>
			    </div>

			    <div class="directions-step">
			        <div class="directions-line-header">
			            <p class="line-name">Change Trains</p>
			        </div>
			    </div>

			    <div class="directions-step">
			        <div class="directions-line-header">
			            <div class="line-circle" :style="{backgroundColor: '#0099cc'}"></div>
			            <p class="line-name">Blue Line</p>
			            <p class="line-direction">towards Station F</p>
			        </div>
			        <ul>
			            <li> Station C </li>
			            <li> Station D </li>
			            <li> Station E </li>
			        </ul>
			    </div>

			    <div class="directions-step">
			        <div class="directions-line-header">
			            <p class="line-name">Arrive at Station E</p>
			        </div>
			    </div>
			</div>
    </div>
</template>








