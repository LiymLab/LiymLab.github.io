{% for alum in site.data.alumni %}
<hr>
<div id = "{{alum.name}}" style="padding-top: 60px; margin-top: -60px;">
<p><strong>{{alum.name}}</strong> - <em>{{alum.position}}</em><br>
{% if alum.startdate %} {{alum.startdate}} - {% endif %}{{alum.enddate}} <br>
Subsequent Position: {{alum.current}}</p>
</div> {% endfor %}

<!-- <br>
## [Undergrad Interns](https://education.scripps.edu/undergraduate/) -->

<!-- 
{% for sep in site.data.sep %}
<hr>
<div id = "{{sep.name}}" style="padding-top: 60px; margin-top: -60px;">
<p><strong>{{sep.name}}</strong><br>
{% if sep.startdate %} {{sep.startdate}} - {% endif %}{{sep.enddate}} <br>
{% if sep.current %}
Subsequent Position: {{sep.current}}<br>
{% endif %}
</p>
</div> {% endfor %}

<br>
## [High School Interns](https://education.scripps.edu/k-12-outreach/)


{% for visitors in site.data.visitors %}
<hr>
<div id = "{{visitors.name}}" style="padding-top: 60px; margin-top: -60px;">
<p><strong>{{visitors.name}}</strong><br>
{% if visitors.startdate %} {{visitors.startdate}} - {% endif %}{{visitors.enddate}} <br>
{% if visitors.current %}
Subsequent Position: {{visitors.current}}<br>
{% endif %}
</p> -->
<!-- </div> {% endfor %} -->
