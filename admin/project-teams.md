{% macro show_main_text() %}
<div id="main">

<img src="{{baseUrl}}/admin/images/team.png" width="300px"><br>
<small>%%[Picture: The team that was at the top of early Google]%%</small>
<p/>

**When to form teams**

* Team formation will happen in week 3 tutorial.
* {{ module }}T: Your team will be the same on CS2101 side as well.

**Team size**: The default ==team size is five==. 

**Team ID**: This will be given to you after forming teams. It has the form `TUTORIAL_ID-TEAM_NUMBER` e.g, `M11-2` means you are in tutorial M11 (i.e., Mon 1100-1200), team 2.

{{ embed_topic("tutorials.md#tutorialTimetable", "Admin " + icon_embedding + " Tutorials → Tutorial IDs", "projectTeams-tutorialIDs", "3") }}

**Team composition**

We allow some freedom in choosing team members, subject to these constraints:

* All team members should be in the same tutorial. ==Delay forming teams until your place in a tutorial is confirmed.== We do not allow changing tutorials to team up with your preferred team mates.  
* Teams of ==single nationality are not allowed== %%&nbsp;Rationale: to train you to work in multicultural teams.%% However, we allow same nationality teams if the only language common among all team members is English. e.g. an all-Singaporean team that include both Chinese and Malay students.
* No more than one exchange students per team %%Rationale: to increase interaction between exchange students and NUS students.%%
* Gender balanced teams are encouraged. While all-male teams may be unavoidable at times (due to high male percentage in the cohort), all-female teams are highly discouraged.

* Also note that ==**we may modify teams when circumstances call for it**==. There is no avenue for you to object. Staying with your preferred team is not guaranteed.

</div>
{% endmacro %}

{% from "common/macros.njk" import embed_topic with context %}
{% from "common/admin.njk" import show_admin_page with context %}
{{ show_admin_page("project-teams", show_main_text) }}
