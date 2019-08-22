{% macro show_main_text() %}
<div id="main">

<div id="title">

</div>
<div id="body">

<p class="lead" style="color: purple"><md>:far-calendar-check: <include src="project-timeline.md#inception-overview" inline /></md></p>

### Project matters


* **Set up a weekly project meeting time/venue with your team members**
  
  We recommend at least one face-to-face project meeting per week. %%The project meeting time can be used to discuss project related things, but also, can be used as a time for team members to work on the project tasks individually (having all members in the same place will facilitate easier collaboration and more peer-learning).%%

<!--  
* **Play around with AB4**
  
  Download the latest released version %%(i.e., the jar file)%% of AB4 from [its upstream repo]({{module_org}}/addressbook-level4) and play around with it to familiarize with its current features.

-->

* **Decide project direction, target user profile, and problem addressed**
  
  Use your first project meeting to discuss with your team members and decide your project direction, target user profile, and the value proposition of the product, as described in <trigger trigger="click" for="modal:v10-scope">[Admin {{ icon_embedding }} Project Scope]</trigger> 

<modal large title="Admin {{ icon_embedding }} Project Scope (Extract)" id="modal:v10-scope">
  <include src="project-scope.md#project-direction"/>
</modal>


### Implement the following increments while committing code incrementally

Implement the following <tooltip content="in this context, an _increment_ is a Duke _level_ or a Duke _extension_">increments</tooltip> in the given order. As earlier:
   * Commit code at important points. ==Minimally, commit after completing each increment==.
   * After completing each increment,
     * **`git tag`** the commit with the exact increment ID e.g., `Level-4`, `A-Inheritance`
     * **`git push`** the code _and the tags_ to your fork

- If you haven't already implemented classes, do this first:

<box>
<include src="dukeFragment.md" boilerplate var-header="**`A-Classes`: Classes**" var-fragment="extensions.mbdf#A-Classes" />
</box>

- Add different types of tasks: `Level-4`
  - Remember `Level-4` includes `A-Inheritance`
  
<box>
<include src="dukeFragment.md" boilerplate var-header="**`Level-4`: ToDo, Event, Deadline**" var-fragment="text.md#level4" />
<include src="dukeFragment.md" boilerplate var-header="**`A-Inheritance`: Inheritance**" var-fragment="extensions.mbdf#A-Inheritance" />
</box>

- Do some error handling

<box>
<include src="dukeFragment.md" boilerplate var-header="**`Level-5`: Handle Errors**" var-fragment="text.md#level5" />
</box>

- Save data to persistent storage

<box>
<include src="dukeFragment.md" boilerplate var-header="**`Level-7`: Save**" var-fragment="text.md#level7" />
</box>

- Add the capability to identify dates and times to duke

<box>
<include src="dukeFragment.md" boilerplate var-header="**`Level-8`: Dates and Times**" var-fragment="text.md#level8" />
</box>

- If applicable, use __Enums__ and __Varargs__

<box>
<include src="dukeFragment.md" boilerplate var-header="**`A-Enums`: Enums**" var-tag="optional" var-fragment="extensions.mbdf#A-Enums" />
<include src="dukeFragment.md" boilerplate var-header="**`A-Varargs`: Varargs**" var-tag="optional" var-fragment="extensions.mbdf#A-Varargs" />
</box>



</div>
</div>
{% endmacro %}

{% from "common/admin.njk" import show_admin_page with context %}
{{ show_admin_page("project-w03-inception", show_main_text) }}
