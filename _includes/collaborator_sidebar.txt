
<h1>Featured Tutorials</h1>
<div class="container-fluid">
	<p><a href="https://scholar.google.com/citations?user=DTb9YvMAAAAJ">Google Scholar Profile</a> for a full tutorial list.</p>
{% for tutorial in site.data.tutorials %}
<hr>
<div class="row" style="padding-top: 60px; margin-top: -60px;" id="{{tutorial.pmid}}">
<div style="font-size: 120% !important;">{{ tutorial.citation | markdownify }}</div>
	<div class="col-sm-6">
		<img class = "img-fluid" src = "{{tutorial.image}}" alt = "Key Figure" style="max-height: 200px;">
	</div>
	<ul class="col-sm-6">
			<strong>Access the paper</strong>
			<!--PMID-->
			{% if tutorial.pmid %}
			<li>PMID: <a href="http://www.ncbi.nlm.nih.gov/pubmed/{{tutorial.pmid}}" alt = "pubmed link: {{tutorial.pmid}}"> {{tutorial.pmid}}</a></li>
			{% endif %}

			<!--PMCID - optional -->
			{% if tutorial.pmcid %}
			<li>PMCID: <a href="http://www.ncbi.nlm.nih.gov/pmc/articles/{{tutorial.pmcid}}" alt = "pubmed central link: {{tutorial.pmcid}}"> {{tutorial.pmcid}}</a></li>
			{% endif %}

			<!--Biorxiv - optional -->
			{% if tutorial.biorxiv %}
			<li>Biorxiv Preprint: <a href="http://dx.doi.org/10.1101/{{tutorial.biorxiv}}" alt = "biorxiv preprint link: {{tutorial.biorxiv}}"> {{tutorial.biorxiv | split: "." | last }}</a></li>
			{% endif %}

			<!--Arxiv - optional -->
			{% if tutorial.arxiv %}
			<li>arXiv Preprint: <a href="https://arxiv.org/abs/{{tutorial.arxiv}}" alt = "arxiv preprint link: {{tutorial.arxiv}}"> {{tutorial.arxiv}}</a></li>
			{% endif %}

			<!--Chemrxiv - optional -->
			{% if tutorial.chemrxiv %}
			<li>ChemRxiv Preprint: <a href=" https://doi.org/10.26434/chemrxiv.{{tutorial.chemrxiv}}" alt = "chemrxiv preprint link: {{tutorial.chemrxiv}}"> {{tutorial.chemrxiv}}</a></li>
			{% endif %}

			<!-- URL -->
			<li><a href="{{tutorial.url}}" alt = "URL"> Full Text</a></li>

			<!-- Datasets - optional -->
			{% if tutorial.data %}
			<li>Online Dataset{% if tutorial.data.size > 1 %}s{% endif %}:
				{% if tutorial.data.size > 1 %}
				<ul>
					{% for dataset in tutorial.data %}
					<li><a href="http://dx.doi.org/{{dataset}}" alt = "sbgrid data repository">doi:{{dataset}}</a></li>
					{% endfor %}
				</ul>
				{% else %}
				<a href="http://dx.doi.org/{{tutorial.data}}" alt = "sbgrid data repository">doi:{{tutorial.data}}</a>
				{% endif %}
			</li>
			{% endif %}

			<!--PDBS - optional-->
			{% if tutorial.pdbs %}
			<li>Deposited Structure{% if tutorial.pdbs.size > 1 %}s{% endif %}:
				{% for code in tutorial.pdbs %}
				<a href="http://www.rcsb.org/pdb/explore/explore.do?structureId={{code}}">{{code}}</a>{% unless forloop.last %}, {% endunless %}
				{% endfor %}
			</li>
			{% endif %}

			<!--EMBDS - optional-->
			{% if tutorial.emdbs %}
			<li>Deposited Map{% if tutorial.emdbs.size > 1 %}s{% endif %}:
				{% for code in tutorial.emdbs %}
				<a href="http://www.ebi.ac.uk/pdbe/entry/emdb/EMD-{{code}}">{{code}}</a>{% unless forloop.last %}, {% endunless %}
				{% endfor %}
			</li>
			{% endif %}

			<!--pairs of maps and models - optional-->
			{% if tutorial.paired_maps_and_models %}
			<li>Deposited Structure{% if tutorial.paired_maps_and_models.size > 1 %}s{% endif %} and Map{% if tutorial.paired_maps_and_models.size > 1 %}s{% endif %}:
				{% for pair in tutorial.paired_maps_and_models %}
				<a href="http://www.rcsb.org/pdb/explore/explore.do?structureId={{pair.pdb}}">{{pair.pdb}}</a>/<a href="http://www.ebi.ac.uk/pdbe/entry/emdb/EMD-{{pair.emdb}}">{{pair.emdb}}</a>{% unless forloop.last %}, {% endunless %}
				{% endfor %}
			</li>
			{% endif %}

			<!--zenodo records - optional-->
			{% if tutorial.zenodo %}
			<li>Zenodo Record{% if tutorial.zenodo.size > 1 %}s{% endif %}:
				{% for record in tutorial.zenodo %}
				<a href="https://doi.org/10.5281/zenodo.{{record.code}}"><img src="https://zenodo.org/badge/DOI/10.5281/zenodo.{{record.code}}.svg" alt="DOI"></a>{% if record.description %} ({{record.description}}){% endif %}{% unless forloop.last %}, {% endunless %}
				{% endfor %}
			</li>
			{% endif %}

			<!--Extra junk-->
			<!-- <strong>Additional Links</strong>
			{% for link in tutorial.links %}
			<li><a href="{{link.url}}" alt="{{link.name}}">{{link.name}}</a></li>
			{% endfor %} -->
	</ul>
</div> <br>
{% endfor %}
</div>
