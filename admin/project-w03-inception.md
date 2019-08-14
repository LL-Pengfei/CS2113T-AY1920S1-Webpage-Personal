{% macro show_main_text() %}
<div id="main">

<div id="title">

</div>
<div id="body">

<p class="lead" style="color: purple"><md>:far-calendar-check: <include src="project-timeline.md#inception-overview" inline /></md></p>

<!--
It is not too early to set an overall direction for your project.

* **Set up a weekly project meeting time/venue with your team members**
  
  We recommend at least one face-to-face project meeting per week. %%The project meeting time can be used to discuss project related things, but also, can be used as a time for team members to work on the project tasks individually (having all members in the same place will facilitate easier collaboration and more peer-learning).%%
  
* **Play around with AB4**
  
  Download the latest released version %%(i.e., the jar file)%% of AB4 from [its upstream repo]({{module_org}}/addressbook-level4) and play around with it to familiarize with its current features.

* **Decide project direction, target user profile, and problem addressed**
  
  Use your first project meeting to discuss with your team members and decide your project direction, target user profile, and the value proposition of the product, as described in <trigger trigger="click" for="modal:v10-scope">[Admin {{ icon_embedding }} Project Scope]</trigger> 

<modal large title="Admin {{ icon_embedding }} Project Scope (Extract)" id="modal:v10-scope">
  <include src="project-scope.md#project-direction"/>
</modal>

<br><br>

<box>

<include src="dukeFragment.md" boilerplate var-header="**`Level-4`: ToDo, Event, Deadline**" var-fragment="text.md#level4" />
<include src="dukeFragment.md" boilerplate var-header="**`A-TextUiTesting`: Text UI Testing**" var-tag="optional" var-fragment="extensions.mbdf#A-TextUiTesting" />
<include src="dukeFragment.md" boilerplate var-header="**`Level-5`: Handle Errors**" var-fragment="text.md#level5" />
<include src="dukeFragment.md" boilerplate var-header="**`Level-6`: Delete**" var-fragment="text.md#level6" />
<include src="dukeFragment.md" boilerplate var-header="**`A-Enums`: Enums**" var-tag="if-applicable" var-fragment="extensions.mbdf#A-Enums" />
<include src="dukeFragment.md" boilerplate var-header="**`Level-7`: Save**" var-fragment="text.md#level7" />
<include src="dukeFragment.md" boilerplate var-header="**`Level-8`: Dates and Times**" var-fragment="text.md#level8" />
<include src="dukeFragment.md" boilerplate var-header="**`A-MoreOOP`: More OOP**" var-fragment="extensions.mbdf#A-MoreOOP" />
<include src="dukeFragment.md" boilerplate var-header="**`A-Packages`: Java Packages**" var-tag="optional" var-fragment="extensions.mbdf#A-Packages" />
<include src="dukeFragment.md" boilerplate var-header="**`A-JUnit`: JUnit Testing**" var-fragment="extensions.mbdf#A-JUnit" />
<include src="dukeFragment.md" boilerplate var-header="**`A-Jar`: JAR file**" var-fragment="extensions.mbdf#A-Jar" />
<include src="dukeFragment.md" boilerplate var-header="**`A-JavaDoc`: JavaDoc**" var-fragment="extensions.mbdf#A-JavaDoc" />
<include src="dukeFragment.md" boilerplate var-header="**`A-CodingStandard`: Coding Standard**" var-fragment="extensions.mbdf#A-CodingStandard" />
<include src="dukeFragment.md" boilerplate var-header="**`Level-9`: Find**" var-fragment="text.md#level9" />
<include src="dukeFragment.md" boilerplate var-header="**`A-Gradle`: Gradle**" var-fragment="extensions.mbdf#A-Gradle" />
<include src="dukeFragment.md" boilerplate var-header="**`A-CheckStyle`: CheckStyle**" var-tag="optional" var-fragment="extensions.mbdf#A-CheckStyle" />
<include src="dukeFragment.md" boilerplate var-header="**`Level-10`: GUI**" var-fragment="text.md#level10" />
<include src="dukeFragment.md" boilerplate var-header="**`A-Varargs`: Varargs**" var-tag="if-applicable" var-fragment="extensions.mbdf#A-Varargs" />
<include src="dukeFragment.md" boilerplate var-header="**`A-Assertions`**" var-fragment="extensions.mbdf#A-Assertions" />
<include src="dukeFragment.md" boilerplate var-header="**`A-CodeQuality`**" var-fragment="extensions.mbdf#A-CodeQuality" />
<include src="dukeFragment.md" boilerplate var-header="**`A-Lambdas`**" var-tag="optional" var-fragment="extensions.mbdf#A-Lambdas" />
<include src="dukeFragment.md" boilerplate var-header="**`A-Streams`**" var-tag="optional" var-fragment="extensions.mbdf#A-Streams" />
<include src="dukeFragment.md" boilerplate var-header="**`A-Travis`: Travis**" var-tag="optional" var-fragment="extensions.mbdf#A-Travis" />
<include src="dukeFragment.md" boilerplate var-header="**`A-UserGuide`: User Guide**" var-fragment="extensions.mbdf#A-UserGuide" />
<include src="dukeFragment.md" boilerplate var-header="**`A-Release`: Release**" var-fragment="extensions.mbdf#A-Release" />

</box>

-->

</div>
</div>
{% endmacro %}

{% from "common/admin.njk" import show_admin_page with context %}
{{ show_admin_page("project-w03-inception", show_main_text) }}
