---
layout: page
title: Road Surface Temperature
---

Monthly mean for day-time and night-time from 1986 to 2100


<iframe src="MeanRST_2000_Jan_day.html" width="900" height="700"></iframe> 




# RST Interactive Plots

<select id="plotDropdown">
  <option value="plot1">MeanRST 2000 Jan</option>
  <option value="plot2">MeanRST 2000 Jul</option>
  <option value="plot3">MeanRST 2018 Jan</option>
  <option value="plot4">MeanRST 2018 Jul</option>
</select>

<div id="plot-container">
  <div id="plot1" class="active">
    <object type="text/html" data="MeanRST_2000_Jan_day.html" style="width:100%; height:700px;"></object>
  </div>
  <div id="plot2">
    <object type="text/html" data="MeanRST_2000_Jul_day.html" style="width:100%; height:700px;"></object>
  </div>
  <div id="plot3">
    <object type="text/html" data="MeanRST_2018_Jan_day.html" style="width:100%; height:700px;"></object>
  </div>
  <div id="plot4">
    <object type="text/html" data="MeanRST_2018_Jul_day.html" style="width:100%; height:700px;"></object>
  </div>
</div>

<style>
#plot-container > div { display: none; }
#plot-container > div.active { display: block; }
select { margin-bottom: 20px; padding: 5px 10px; font-size: 16px; }
</style>

<script>
const dropdown = document.getElementById('plotDropdown');
const plots = document.querySelectorAll('#plot-container > div');

dropdown.addEventListener('change', () => {
  plots.forEach(div => div.classList.remove('active'));
  document.getElementById(dropdown.value).classList.add('active');
});
</script>
