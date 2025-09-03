---
layout: page
title: Road Surface Temperature
---

Monthly mean for day-time and night-time from 1986 to 2100

<label for="yearSlider">Year:</label>
<input type="range" id="yearSlider" min="2000" max="2018" step="18" value="2000">

<select id="monthDropdown">
  <option value="Jan">January</option>
  <option value="Jul">July</option>
</select>

<div id="plot-container">
  <div id="2000_Jan" class="active">
    <object type="text/html" data="MeanRST_2000_Jan_day.html"></object>
  </div>
  <div id="2000_Jul">
    <object type="text/html" data="MeanRST_2000_Jul_day.html"></object>
  </div>
  <div id="2018_Jan">
    <object type="text/html" data="MeanRST_2018_Jan_day.html"></object>
  </div>
  <div id="2018_Jul">
    <object type="text/html" data="MeanRST_2018_Jul_day.html"></object>
  </div>
</div>

<style>
/* Slider and dropdown styling */
#yearSlider { width: 200px; margin: 10px; }
select { margin: 10px; padding: 5px 10px; font-size: 16px; }

/* Plot container styling */
#plot-container {
  position: relative;
  width: 100%;
  max-width: 1000px;
  height: 600px;
  margin: 0 auto;
  overflow: hidden; /* hide scrollbars */
}

/* Each plot div */
#plot-container > div {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0;
  transition: opacity 0.5s ease-in-out;
  pointer-events: none;
}

/* Active plot */
#plot-container > div.active {
  opacity: 1;
  pointer-events: auto;
}

/* Make the <object> fill container fully and hide its internal scroll */
#plot-container object {
  width: 100%;
  height: 100%;
  border: none;
  overflow: hidden;
  transform: scale(1);
  transform-origin: top left;
}
</style>

<script>
const yearSlider = document.getElementById('yearSlider');
const monthDropdown = document.getElementById('monthDropdown');
const plots = document.querySelectorAll('#plot-container > div');

function updatePlot() {
  const year = yearSlider.value;
  const month = monthDropdown.value;
  const selected = year + '_' + month;
  
  plots.forEach(div => div.classList.remove('active'));
  const activeDiv = document.getElementById(selected);
  if (activeDiv) activeDiv.classList.add('active');
}

// Update plot when either control changes
yearSlider.addEventListener('input', updatePlot);
monthDropdown.addEventListener('change', updatePlot);

// Initialize
updatePlot();
</script>

