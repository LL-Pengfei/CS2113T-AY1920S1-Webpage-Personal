{% macro show_main_text() %} 
<div id="main">

In this semester, we are going to enhance [an AddressBook application](https://se-edu.github.io/addressbook-level4/).

<img src="https://github.com/se-edu/addressbook-level4/raw/master/docs/images/Ui.png" width="600"/>
<p/>

This product is meant for users who can type fast, and prefer typing over mouse/voice commands. Therefore, ==Command Line Interface (CLI) is the primary mode of input.== 

{{ embed_topic("project-constraints.md#constraint-cli", "Admin " + icon_embedding + " Project Contstraints → More info about the 'CLI app' requirement", "projectProduct-constraintCli", "2") }}
<p/>

</div>
{% endmacro %} 

{% from "common/macros.njk" import embed_topic with context %}
{% from "common/admin.njk" import show_admin_page with context %}
{{ show_admin_page("project-product", show_main_text) }}
