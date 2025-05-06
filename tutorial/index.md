---
layout: default
---

<h2><b>Tutorials</b></h2>

<div class="wrapper row3">
  <div id="container">
    <div class="full_width clear">
      <ol>
          {% for project in site.data.tutorials %}
          <hr>
          <div id="{{ project.title | slugify }}" class="row" style="padding-top: 60px; margin-top: -60px;">

              <div class="col-sm-7">
                  <h3>{{ project.title | markdownify }}</h3>
                  <div class="text-justify">
                      {{ project.description | markdownify }}
                      {% if project.url %}
                      <p><a href="{{ project.url }}" class="btn btn-primary">View Tutorial</a></p>
                      {% endif %}
                  </div>
              </div>
              

              <div class="col-sm-5">
                  <img class="img-responsive" 
                       src="{{ project.image }}" 
                       {% if project.altimage %}
                       onmouseover="this.src='{{ project.altimage }}';" 
                       onmouseout="this.src='{{ project.image }}';"
                       {% endif %}
                       alt="{{ project.title | escape }}">
              </div>
          </div>
          {% endfor %}
      </ol>
    </div>
  </div>
</div>
