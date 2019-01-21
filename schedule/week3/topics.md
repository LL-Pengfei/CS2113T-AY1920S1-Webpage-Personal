{% import "common/outcomes.njk" as outcomes with context %}
{% from "schedule/index.md" import all_outcomes with context %}

<box type="warning">

****OOP is carried forward from week 2****

</box>

{{ outcomes.show_week_schedule("3", all_outcomes) }}