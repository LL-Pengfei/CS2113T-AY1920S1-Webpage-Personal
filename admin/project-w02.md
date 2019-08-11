{% macro show_main_text() %}
<div id="main">

<div id="title">

</div>


<div id="body">

<p class="lead" style="color: purple"><md>:far-calendar-check: <include src="project-timeline.md#warmup-overview" inline /></md></p>

### Set up prerequisites

**Ensure you have met the following prerequisites:**

<box>

**Prerequisites**:

* Install Git in your computer.
* Have a GitHub account.
* Recommended: Installed an IDE in your computer.

{{ embed_topic("tools.md#main", "Admin " + icon_embedding + " **Tools**", "W02-tools", "2") }}

</box>


### Set up the project in your computer

<box>

1. Fork [{{ module_org }}/duke]({{ module_org }}/duke).
1.  ==Ensure the issue tracker of your fork is enabled.== %%Reason: our bots will be posting your weekly progress reports on the issue tracker of your fork.%%
1. Clone the fork onto your computer.
1. Set up the project in your IDE as explained in the README file.

</box>

### Implement increments while committing code frequently

Implement the following <tooltip content="in this context, an _increment_ is a Duke _level_ or a Duke _extension_">increments</tooltip> in the given order.
   * Commit code at important points. ==Minimally, commit after completing each increment==.
   * After completing each increment,
     * **`git tag`** the commit with the exact increment ID e.g., `Level-2`, `A-TextUiTesting`
     * **`git push`** the code _and the tags_ to your fork

<box>

<include src="dukeFragment.md" boilerplate var-header="**`Level-1`: Greet, Echo, Exit**" var-fragment="text.md#level1" />
<include src="dukeFragment.md" boilerplate var-header="**`Level-2`: Add, List**" var-fragment="text.md#level2" />
<include src="dukeFragment.md" boilerplate var-header="**`Level-3`: Mark as Done**" var-fragment="text.md#level3" />

</box>

</div>
</div>
{% endmacro %}

{% from "common/macros.njk" import embed_topic with context %}
{% from "common/admin.njk" import show_admin_page with context %}
{{ show_admin_page("project-w02", show_main_text) }}
