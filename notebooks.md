---
layout: page
title: Notebooks
permalink: /Notebooks/
---

<style type="text/css">
button {
  background:none;
  background-color:transparent;
  box-shadow:none; border:none;
  font-family:inherit; color:inherit;
  border-radius:0;
  cursor:pointer; }

.caret { line-height:0; }
.caret:after { content:""; }
.asc .caret:after {
  width: 0;
  height: 0;
  border-left: 3px solid transparent;
  border-right: 3px solid transparent;
  border-top: 3px solid #808080;
  content: "";
  position: relative;
  top: -3px;
  right: -4px;
  font-size:0; }
.desc .caret:after {
  width: 0;
  height: 0;
  border-left: 3px solid transparent;
  border-right: 3px solid transparent;
  border-bottom: 3px solid #808080;
  content: "";
  position: relative;
  top: -7px;
  right: -4px;
  font-size:0; }
.sort .caret { display:none; }
.sort.asc .caret { display:inline-block; }
.sort.desc .caret { display:inline-block; }
.sortUnitPrice, .sortQty, .sortTotal { min-width:90px; }

</style>

Below is a collection of contributed Jupyter Notebooks.

<div id="tableID">
<div class="row" style="margin-bottom:10px;">
		<input type="text" class="search form-control" placeholder="Search" />
</div>
<table class="table">
	<thead>
		<th><button type="button" class="sort" data-sort="sortName">Name<i class="caret"></i></button></th>
		<th><button type="button" class="sort" data-sort="sortBinder">Binder</button></th>
		<th><button type="button" class="sort textright" data-sort="sortAzure">Azure Notebook</button></th>
		<th><button type="button" class="sort textright" data-sort="sortColab">Google CoLab</button></th>
	</thead>
    <!-- IMPORTANT, class="list" must be on tbody -->
    <tbody class="list">
{% for worksheet in site.data.notebooks %}
	<tr>
		<td class="sortName">
			<a href="{{ worksheet.url }}">
				{{ worksheet.name }}
			</a>
		</td>
        <td class="sortBinder">
	{% if worksheet.binder %}
			<a href="https://mybinder.org/{{ worksheet.binder }}">
				<img src="https://mybinder.org/badge_logo.svg">
			</a>
	{% endif %}
		</td>
        <td class="sortAzure">
	{% if worksheet.azure_notebook %}
			<a href="https://notebooks.azure.com/{{ worksheet.azure_notebook }}">
				<img src="https://notebooks.azure.com/launch.svg">
			</a>
	{% endif %}
		</td>
        <td class="sortColab">
	{% if worksheet.colab %}
			<a href="https://colab.research.google.com/{{ worksheet.colab }}">
				<img src="https://colab.research.google.com/assets/colab-badge.svg">
			</a>
	{% endif %}
		</td>
      </tr>
{% endfor %}
	</tbody>

</table>
</div>
    
<script src="//cdnjs.cloudflare.com/ajax/libs/list.js/1.5.0/list.min.js"></script>
<script type="text/javascript">
    var options = {
        valueNames: [ 'sortName']
    };
    var contactList = new List('tableID', options);
</script>
     
