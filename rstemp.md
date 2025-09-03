---
layout: page
title: Road Surface Temperature
---

Monthly mean for day-time and night-time from 1986 to 2100


<iframe src="MeanRST_2000_Jan_day.html" width="900" height="700"></iframe> 






# RST Interactive Plots

<select id="yearDropdown">
  <option value="2000">Year 2000</option>
  <option value="2018">Year 2018</option>
</select>

<select id="monthDropdown">
  <option value="Jan">January</option>
  <option value="Jul">July</option>
</select>

<div id="plot-container">
  <div id="2000_Jan" class="active">
    <object type="text/html" data="MeanRST_2000_Jan_day.html" style="width:100%; height:600px;"></object>
  </div>
  <div id="2000_Jul">
    <object type="text/html" data="MeanRST_2000_Jul_day.html" style="width:100%; height:600px;"></object>
  </div>
  <div id="2018_Jan">
    <object type="text/html" data="MeanRST_2018_Jan_day.html" style="width:100%; height:600px;"></object>
  </div>
  <div id="2018_Jul">
    <object type="text/html" data="MeanRST_2018_Jul_day.html" style="width:100%; height:600px;"></object>
  </div>
</div>

<style>
#plot-container > div { display: none; }
#plot-container > div.active { display: block; }
select { margin: 10px 10px 20px 0; padding: 5px 10px; font-size: 16px; }
</style>

<script>
const yearDropdown = document.getElementById('yearDropdown');
const monthDropdown = document.getElementById('monthDropdown');
const plots = document.querySelectorAll('#plot-container > div');

function updatePlot() {
  const selected = yearDropdown.value + '_' + monthDropdown.value;
  plots.forEach(div => div.classList.remove('active'));
  const activeDiv = document.getElementById(selected);
  if (activeDiv) activeDiv.classList.add('active');
}

// Update plot when either dropdown changes
yearDropdown.addEventListener('change', updatePlot);
monthDropdown.addEventListener('change', updatePlot);

// Initialize display
updatePlot();
</script>

dropdown.addEventListener('change', () => {
  plots.forEach(div => div.classList.remove('active'));
  document.getElementById(dropdown.value).classList.add('active');
});
</script>
