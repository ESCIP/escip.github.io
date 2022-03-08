---
layout: page
title: Notebooks
permalink: /Notebooks/
---

Use the search box below to find contributed Jupyter Notebooks to use
in your course.  If you have a Jupyter Notebook to contribute, please
fill out this [form](/notebook-submission-form.html).


<!-- Make the table wider than the column (150%) but not wider than
the 90% of the view port (90vw) and keep the table centered. Once the
table becomes too narrow, turn on a scroll bar.  adapted from
https://stackoverflow.com/a/24895631 -->
<div id="tableID" style="overflow-x:scroll;
width: min(100vw, 110%); position: relative; left: calc( max(-55%,
-50vw) + 50%);"> <div class="row" style="margin-bottom:10px;">
    <!-- 'fuzzy-search' combines multiple search terms with AND and
    searches across all columns.  'search' uses an exact text
    search. -->
	<input type="text" class="fuzzy-search form-control" placeholder="Search" />
</div>
<table class="notebook-table">
<thead>
		<th>
			<button type="button" class="sort" data-sort="sortName">
				<div class="text">Name</div><i class="unsorted_caret"></i><i class="sorted_caret"></i>
			</button>
		</th>
		<th>
			<button type="button" class="sort" data-sort="sortAuthor">
				<div class="text">Author</div><i class="unsorted_caret"></i><i class="sorted_caret"></i>
			</button>
		</th>
		<th>
			<button type="button" class="sort" data-sort="sortKeywords">
				<div class="text">Keywords</div><i class="unsorted_caret"></i><i class="sorted_caret"></i>
			</button>
		</th>
		<th>
			<button type="button" class="sort" data-sort="sortLevel">
				<div class="text">Level</div><i class="unsorted_caret"></i><i class="sorted_caret"></i>
			</button>
		</th>
		<th>
			<button type="button" class="sort" data-sort="sortBinder">
				<div class="text">Binder</div><i class="unsorted_caret"></i><i class="sorted_caret"></i>
			</button>
		</th>
		<!-- <th><button type="button" class="sort textright" data-sort="sortAzure">Azure Notebook</button></th> -->
		<th>
			<button type="button" class="sort" data-sort="sortColab">
				<div class="text">Google CoLab</div><i class="unsorted_caret"></i><i class="sorted_caret"></i>
			</button>
		</th>
	</thead>
    <!-- IMPORTANT, class="list" must be on tbody -->
    <tbody class="list">
<!-- Go through each row in the CSV file in reverse order. Newest entries (bottom) row will appear at the top of the table.-->
{% for worksheet in site.data.notebooks reversed %}
	<tr>
		<td class="sortName">
			<a href="{{ worksheet.url }}">
				{{ worksheet.name }}
			</a>
		</td>
		<td class="sortAuthor">
			<a href="mailto:{{ worksheet.email }}">
				{{ worksheet.author }}
			</a>
		</td>
		<td class="sortKeywords">
			{{ worksheet.keywords }}
		</td>
		<td class="sortLevel">
			{{ worksheet.level }}
		</td>
        <td class="sortBinder">
	{% if worksheet.binder %}
			<a href="{{ worksheet.binder }}">
				<img src="https://mybinder.org/badge_logo.svg">
			</a>
	{% endif %}
		</td>
    <!--     <td class="sortAzure"> -->
	<!-- {% if worksheet.azure_notebook %} -->
	<!-- 		<a href="https://notebooks.azure.com/{{ worksheet.azure_notebook }}"> -->
	<!-- 			<img src="https://notebooks.azure.com/launch.svg"> -->
	<!-- 		</a> -->
	<!-- {% endif %} -->
	<!-- 	</td> -->
        <td class="sortColab">
	{% if worksheet.colab %}
			<a href="{{ worksheet.colab }}">
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
        valueNames: [ 'sortName', 'sortAuthor', 'sortKeywords', 'sortLevel', 'sortBinder', 'sortColab'],
    };
    var contactList = new List('tableID', options);
</script>
     
