# Agenda (Eastern Time)
## Friday, May 8th

|Time|topic|
| :---| :---|
{% for talk in renderyaml|sort(attribute='time') %}|{{talk['time']}}|<b>{{talk['title']}}{% if talk['binder'] %} [![Binder](https://mybinder.org/badge_logo.svg)]({{talk['binder']}}){% endif %}</b><br><br>{% if talk['abstract'] %}{{talk['abstract']}}<br><br>{% endif %}{% if talk['speaker'] %}{% for speaker in talk['speaker'] %}{{speaker['name']}}{% if speaker['twitter'] %}{% set handle = speaker['twitter'].split('@') %} [{{speaker['twitter']}}](http://twitter.com/{{handle[1]}}){% endif %}, {{speaker['job_title']}}, {{speaker['company']}}<br>{% endfor %}{% endif %}|
{% endfor %}