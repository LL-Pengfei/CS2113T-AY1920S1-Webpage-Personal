{% macro show_main_text() %}
<div id="main">

<div id="title">

</div>
<div id="body">

<p class="lead" style="color: purple"><md>:far-calendar-check: <include src="project-timeline.md#warmup-overview" inline /></md></p>

<include src="dukeFragment.md" boilerplate var-header="**`Level-1`: Greet, Echo, Exit**" var-fragment="text.md#level1" />
<include src="dukeFragment.md" boilerplate var-header="**`Level-2`: Add, List**" var-fragment="text.md#level2" />
<include src="dukeFragment.md" boilerplate var-header="**`Level-3`: Mark as Done**" var-fragment="text.md#level3" />
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

</div>
</div>
{% endmacro %}

{% from "common/admin.njk" import show_admin_page with context %}
{{ show_admin_page("project-w02", show_main_text) }}
