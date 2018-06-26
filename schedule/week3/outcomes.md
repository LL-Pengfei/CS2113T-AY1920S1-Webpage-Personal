{% import "se-book-adapted/config.njk" as config with context %}

{% macro show_priority_style_untrimmed(level) %}
{% set label_style = {"1": "danger", "2": "warning", "3": "info", "4": "success"} %}
{{ label_style[level] }}
{% endmacro %}


{% macro show_priority_style(level) %}{{ show_priority_style_untrimmed(level) | trim }}{% endmacro %}

{% macro show_stars_untrimmed(level) %}
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


{% macro show_stars(level) %}{{ show_stars_untrimmed(level) | trim }}{% endmacro %}

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

{% macro show_evidence(chapter, unit_location) %}
{{ dashed_line | safe}}

{{evidence}}

<include src="../evidence/{{ chapter }}.md#{{ unit_location | replace("/", "_")}}" />

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
  {% if not unit.omit_evidence %}
  {{ show_evidence(chapter, path) }}
  {% endif %}
</panel>
{% endmacro %}


{% macro get_unit_priority(unit)%}
{% if unit.priority %} 
  {{unit.priority}}
{% elseif unit.location %}
  {% set chapter = unit.location[0] %}
  {% set path_as_array = unit.location.slice(1,4) %}
  {{ config.get_priority(chapter, path_as_array) }}
{% else %}
  {{ 5 }}
{% endif %}
{% endmacro %}

{% macro get_collective_priority(entries)%} 
{% set priority = 4 %} 
{% for entry in entries %} 
  {% set entry_priority = get_unit_priority(entry) | trim | int %} 
  {% if (entry_priority) < priority %} 
    {% set priority = entry_priority %}
  {% endif %}
{% endfor %}
{{ priority }}
{% endmacro %}


{% macro show_outcome(entries, params={week_num: "n/a", starting_index: "n/a", outcome: "n/a"}) %}
{% if not params.outcome.priority %}
  {% set priority = get_collective_priority(entries) | trim %}
{% else %}
  {% set priority = params.outcome.priority %}
{% endif %} 
{% set  prefix = "W" + params.week_num + "." + params.starting_index%}
{% set letters = "abcdefghijklmnop" | list %} 
{% set letter_index = 0 %} 
<panel no-close expanded >
<span slot="header" class="panel-title"><md>`{{ prefix | trim }}` **{{ params.outcome.heading }}** {{ show_stars(priority) }}</md> </span>
{% if params.outcome.file %} 
  <include src="{{ params.outcome.file }}" />
{% else %}
  {% for entry in entries  %} 
    {% if entry.location %} 
{{ show_unit(prefix + letters[letter_index], entry) }}
      {% set letter_index = letter_index + 1 %}
    {% endif %}
  {% endfor %}
{% endif %}
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
  {name: "Refactoring"}, 
    {heading: "Can refactor code at a basic level"},
      {location: ["refactoring", "what"]},
      {location: ["intellij", "refactoring"]},
      {location: ["refactoring", "how"]},
      {location: ["refactoring", "when"]},
  {name: "Code Quality"}, 
    {heading: "Can follow a simple style guide"},
      {location: ["codeQuality", "introduction", "basic"], omit_evidence: true},
      {location: ["codeQuality", "followStandard", "introduction"]},
      {location: ["codeQuality", "followStandard", "basic"]},
      {location: ["codeQuality", "followStandard", "intermediate"]},
    {heading: "Can improve code readability"},
      {location: ["codeQuality", "maximiseReadability", "introduction"], omit_evidence: true},
      {location: ["codeQuality", "maximiseReadability", "basic", "avoidLongMethods"], omit_evidence: true},
      {location: ["codeQuality", "maximiseReadability", "basic", "avoidDeepNesting"], omit_evidence: true},
      {location: ["codeQuality", "maximiseReadability", "basic", "avoidComplicatedExpressions"], omit_evidence: true},
      {location: ["codeQuality", "maximiseReadability", "basic", "avoidMagicNumbers"], omit_evidence: true},
      {location: ["codeQuality", "maximiseReadability", "basic", "makeCodeObvious"], omit_evidence: true},
      {location: ["codeQuality", "maximiseReadability", "intermediate", "structureCodeLogically"], omit_evidence: true},
      {location: ["codeQuality", "maximiseReadability", "intermediate", "dontTripReader"], omit_evidence: true},
      {location: ["codeQuality", "maximiseReadability", "intermediate", "practiceKISSing"], omit_evidence: true},
      {location: ["codeQuality", "maximiseReadability", "intermediate", "avoidPrematureOptimizations"], omit_evidence: true},
      {location: ["codeQuality", "maximiseReadability", "intermediate", "slapHard"], omit_evidence: true},
      {location: ["codeQuality", "maximiseReadability", "advanced", "makeHappyPathProminent"], omit_evidence: true},
    {heading: "Can use good naming"},
      {location: ["codeQuality", "nameWell", "introduction"], omit_evidence: true},
      {location: ["codeQuality", "nameWell", "basic", "nounsAndVerbsAsNames"], omit_evidence: true},
      {location: ["codeQuality", "nameWell", "basic", "useStandardWords"], omit_evidence: true},
      {location: ["codeQuality", "nameWell", "intermediate", "useNameExplain"], omit_evidence: true},
      {location: ["codeQuality", "nameWell", "intermediate", "notTooLongNorShort"], omit_evidence: true},
      {location: ["codeQuality", "nameWell", "intermediate", "avoidMisleadingNames"], omit_evidence: true},
    {heading: "Can avoid unsafe coding practices"},
      {location: ["codeQuality", "avoidShortcuts", "introduction"], omit_evidence: true},
      {location: ["codeQuality", "avoidShortcuts", "basic", "useDefaultBranch"], omit_evidence: true},
      {location: ["codeQuality", "avoidShortcuts", "basic", "dontRecycleVarsOrParams"], omit_evidence: true},
      {location: ["codeQuality", "avoidShortcuts", "basic", "avoidEmptyCatchBlocks"], omit_evidence: true},
      {location: ["codeQuality", "avoidShortcuts", "basic", "deleteDeadCode"], omit_evidence: true},
      {location: ["codeQuality", "avoidShortcuts", "intermediate", "minimiseVariableScope"], omit_evidence: true},
      {location: ["codeQuality", "avoidShortcuts", "intermediate", "minimiseCodeDuplication"], omit_evidence: true},
    {heading: "Can write good code comments"},
      {location: ["codeQuality", "commentMinimally", "introduction"], omit_evidence: true},
      {location: ["codeQuality", "commentMinimally", "basic", "dontRepeatObvious"], omit_evidence: true},
      {location: ["codeQuality", "commentMinimally", "basic", "writeToReader"], omit_evidence: true},
      {location: ["codeQuality", "commentMinimally", "intermediate", "explainWhatWhyNotHow"], omit_evidence: true},
  {name: "IDEs"}, 
    {heading: "Can use intermediate level features of an IDE"},
      {location: ["ides", "debugging", "what"], omit_evidence: true},
      {location: ["intellij", "debuggingBasic"]},
      {location: ["intellij", "productivityShortcuts"]},
  {name: "Revision Control"}, 
    {heading: "Can communicate with a remote repo"},
      {location: ["revisionControl", "remoteRepositories"], omit_evidence: true},
      {location: ["gitAndGithub", "clone"]},
      {location: ["gitAndGithub", "pull"]},
      {location: ["gitAndGithub", "push"]},
    {heading: "Can traverse Git history"},
      {location: ["revisionControl", "usingHistory"], omit_evidence: true},
      {location: ["gitAndGithub", "checkout"]},
      {location: ["gitAndGithub", "tag"]},
      {location: ["gitAndGithub", "stash"]},
  {name: "Other"}, 
    {heading: "Can work with a 1KLoC code base ==[Compulsory]==", priority: "1", file: "outcome-1kloc.md"}
]%}

{{ show_week_schedule("3", all_outcomes) }}

</div>


