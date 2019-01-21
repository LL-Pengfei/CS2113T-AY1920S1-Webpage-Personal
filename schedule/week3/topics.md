{% import "common/outcomes.njk" as outcomes with context %}
{% from "schedule/index.md" import all_outcomes with context %}

* <big>****OOP is carried forward from week 2****</big>

{{ outcomes.show_week_schedule("3", all_outcomes) }}