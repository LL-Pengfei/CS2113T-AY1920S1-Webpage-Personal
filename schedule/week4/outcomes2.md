{% import "se-book-adapted/config.njk" as config with context %}

{% macro priority_style(level) %}
{% set label_style = {"1": "danger", "2": "warning", "3": "info", "4": "success"} %}
{{ label_style[level] }}
{% endmacro %}


{% macro show_priority_style(level) %}{{ priority_style(level) | trim }}{% endmacro %}

{% macro show_priority(level) %}
{% if level == "1" %}
  {{ one_star }}
{% elseif level == "2" %}
  {{ two_stars }}
{% elseif level == "3" %}
  {{ three_stars }}
{% elseif level == "4" %}
  {{ four_stars }}
{% else %}
  Unknown level !!! {{ level }}
{% endif %}
{% endmacro %}


{% macro show_stars(level) %}{{ show_priority(level) | trim }}{% endmacro %}

{# -------------- from macros.njk --------------------------- #}

{% macro print_list(entries) %} 
{% for entry in entries %}
{{ loop.index }} {{ entry.week | default("-") + "/" + entry.day | default("-") + "/" + entry.session | default("-") }}
{% endfor %}
{% endmacro %}


{% macro get_start_index_untrimmed(filter_property, filter_value, entries) -%}
{% set start = "-1" %}  
{% for entry in entries %}
{% if start == "-1" and entry[filter_property] == filter_value %} 
  {% set start = loop.index0 %}
  {{ start }}
{% endif %}
{% endfor %}
{%- endmacro %}


{% macro get_start_index(filter_property, filter_value, entries) %}{{ get_start_index_untrimmed(filter_property, filter_value, entries) | trim }}{% endmacro %}


{% macro get_end_index_untrimmed(filter_property, filter_value, start, entries) -%}
{% set end = "-1" %}  
{% for entry in entries %}
{% if loop.index0 < start %} 
  {# start index not reached, no action required #}
{% elseif not entry[filter_property] %}
  {# filter property not present, no action required #}
{% else %}
  {% if entry[filter_property] == filter_value %} 
    {# filter property matched, no action required #}
  {% else %}
    {# filter property value did not match #}
    {% if end == "-1" %} 
      {# first time encountering mismatch; this is the target index #}
      {% set end = loop.index0 %}
    {% endif %}
  {% endif %}
{% endif %}
{% endfor %}
{% if end == "-1" %} 
  {# no mismatch found until the end of the list #}
  {% set end = entries | length %}
{% endif %}
{{ end }}
{%- endmacro %}


{% macro get_end_index(filter_property, filter_value, start, entries) %}{{get_end_index_untrimmed(filter_property, filter_value, start, entries) | trim }}{% endmacro %}


{% macro apply_to(filter_property, filter_value, entries, op, params={})%} 
{% set start = get_start_index(filter_property, filter_value, entries) %} 
{% set end = get_end_index(filter_property, filter_value, start, entries) %} 
{{ op(entries.slice(start, end), params) }}
{% endmacro %}


{% macro show_unit(id_prefix, unit) %}
{% set chapter = unit.location[0] %}
{% set path_as_array = unit.location.slice(1,4) %}
{% set path = path_as_array.join("/") %}
{% set full_path = unit.location.join("/") %}
{% if not unit.priority %}
  {% set priority = config.get_priority(chapter, path_as_array) %}
{% else %}
  {% set priority = unit.priority %}
{% endif %}
<panel type="{{ show_priority_style(priority) }}" no-close >
<span slot="header" class="panel-title"><md>`{{ id_prefix }}` <include src="../../book/{{  full_path }}/text.md#outcomes" inline/> {{ show_stars(priority) }}</md></span>
  <include src="../../book/{{ full_path }}/unit-inElsewhere-asFlat.md" boilerplate />
</panel>
{% endmacro %}

{% macro show_outcome(entries, params={week_num: "n/a", starting_index: "n/a", outcome: "n/a"}) %} 
{% set  prefix = "W" + params.week_num + "." + params.starting_index%}
{% set letters = "abcdefghijklmnop" | list %} 
{% set letter_index = 0 %} 
<panel no-close expanded >
<span slot="header" class="panel-title"><md>`{{ prefix | trim }}` **{{ params.outcome.heading }}** {{ show_stars(params.outcome.priority) }}</md> </span>
{% for entry in entries  %} 
  {% if entry.location %} 
{{ show_unit(prefix + letters[letter_index], entry) }}
{% set letter_index = letter_index + 1 %}
  {% endif %}
{% endfor %}
</panel>
{% endmacro %}


{% macro show_outcome_group(entries, params={name: "n/a", week_num: "n/a", starting_index: "n/a"}) %} 
<span class="activity-desc">{{ params.name }}</span>
<div class="indented">
{% set  outcome_number = params.starting_index | int %} 
{% for entry in entries  %} 
  {% if entry.heading %} 
{{ apply_to("heading", entry.heading, entries, show_outcome, {week_num: params.week_num, starting_index: outcome_number , outcome: entry}) }}
{% set  outcome_number = outcome_number + 1 %}
  {% endif %}
{% endfor %}
</div>
<p/>
{% endmacro %}


{% macro show_week(entries, params={week_num: "n/a"}) %}
{% set i = 1 %} 
{% for entry in entries  %} 
  {% if entry.name %}
{{ apply_to("name", entry.name, entries, show_outcome_group, {name: entry.name, week_num: params.week_num, starting_index: i}) }}
  {% set i = i + apply_to("name", entry.name, entries, count_outcomes) | trim | int %} 
  {% endif %}
{% endfor %}
{% endmacro %}


{% macro count_outcomes(entries, params={})%} 
{% set count = 0 %} 
{% for entry in entries %} 
  {% if entry.heading %} 
    {% set count = count + 1 %}
  {% endif %}
{% endfor %} 
{{ count }}
{% endmacro %}


{% macro show_week_schedule(week_num, entries) %} 
<link rel="stylesheet" href="{{baseUrl}}/css/main.css">
<link rel="stylesheet" href="{{baseUrl}}/css/schedule.css">

<div class="website-content">

## Week {{ week_num }} - Outcomes

<div id="main">

{{ apply_to("week", week_num, entries, show_week, {week_num: week_num}) }}

</div>
</div>

{% endmacro %}


{% set all_outcomes = [
{week: "3"},
  {name: "Design"}, 
    {heading: "Can explain models", priority: "3"}, 
      {location: ["modeling", "introduction", "what"], omit_evidence: true},
      {location: ["modeling", "introduction", "how"]},
    {heading: "Can explain OOP", priority: "1"}, 
      {location: ["oopDesign", "introduction", "what"], omit_evidence: true},
{week: "4"},
  {name: "Design"}, 
    {heading: "Can explain models", priority: "3"}, 
      {location: ["modeling", "introduction", "what"], omit_evidence: true},
      {location: ["modeling", "introduction", "how"]},
    {heading: "Can explain OOP", priority: "1"}, 
      {location: ["oopDesign", "introduction", "what"], omit_evidence: true},
      {location: ["oopDesign", "objects", "basic"]},
      {location: ["oopDesign", "classes", "basic"]},
      {location: ["oopDesign", "objects", "abstraction"], omit_evidence: true},
      {location: ["oopDesign", "objects", "encapsulation"], omit_evidence: true},
    {heading: "Can explain basic object/class structures", priority: "1"}, 
      {location: ["modeling", "modelingStructures", "ooStructures"], omit_evidence: true},
      {location: ["modeling", "modelingStructures", "classDiagramsBasic"]},
      {location: ["uml", "miscellaneous", "objectVsClassDiagrams"], omit_evidence: true},
  {name: "Implementation"},
    {heading: "Can implement classes", priority: "1"},
      {location: ["oopImplementation", "classes"]},
      {location: ["oopImplementation", "associations"]},
    {heading: "Can do exception handling in code", priority: "2"}, 
      {location: ["errorHandling", "introduction", "what"], omit_evidence: true},
      {location: ["errorHandling", "exceptions", "what"], omit_evidence: true},
      {location: ["errorHandling", "exceptions", "how"]},
      {location: ["errorHandling", "exceptions", "when"], omit_evidence: true},
    {heading: "Can use Java enumerations", priority: "3"},
      {location: ["oopDesign", "classes", "enumerations"]},
      {location: ["javaTools", "enums"]},
  {name: "Project Management"}, 
    {heading: "Can create PRs on GitHub", priority: "1"}, 
      {location: ["revisionControl", "branching"]},
      {location: ["gitAndGithub", "branch"]},
      {location: ["gitAndGithub", "createPRs"]},
      {location: ["gitAndGithub", "mergeConflicts"]},
      {location: ["gitAndGithub", "managePRs"]},
{week: "5"},
  {name: "Design"}, 
    {heading: "Can explain models", priority: "3"}, 
      {location: ["modeling", "introduction", "what"], omit_evidence: true},
      {location: ["modeling", "introduction", "how"]},
    {heading: "Can explain OOP", priority: "1"}, 
      {location: ["oopDesign", "introduction", "what"], omit_evidence: true}
]%}

{{ show_week_schedule("4", all_outcomes) }}

</div>