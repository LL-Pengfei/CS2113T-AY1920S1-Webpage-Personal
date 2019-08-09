{% macro show_main_text() %} 
<div id="main">

<!-- In this semester, we are going to enhance [an AddressBook application](https://se-edu.github.io/addressbook-level4/). -->

In this semester, we will implement and enhance a simple personal assistant, [_Duke_](https://github.com/nusCS2113-AY1920S1/duke).
In the initial phase, you will design and develop _Duke_ to manage tasks for a user. A sample interaction with _Duke_ is as shown below.

```
    ____________________________________________________________
      ____        _        
     |  _ \ _   _| | _____ 
     | | | | | | | |/ / _ \
     | |_| | |_| |   <  __/
     |____/ \__,_|_|\_\___|

     Hello! I'm Duke
     What can I do for you?
    ____________________________________________________________

list
    ____________________________________________________________
     Here are the tasks in your list:
     1.[T][✓] read book
     2.[D][✗] return book (by: June 6th)
     3.[E][✗] project meeting (at: Aug 6th 2-4pm)
     4.[T][✓] join sports club
    ____________________________________________________________

todo borrow book
    ____________________________________________________________
     Got it. I've added this task: 
       [T][✗] borrow book
     Now you have 5 tasks in the list.
    ____________________________________________________________

bye
    ____________________________________________________________
     Bye. Hope to see you again soon!
    ____________________________________________________________

```

<!-- img src="https://github.com/se-edu/addressbook-level4/raw/master/docs/images/Ui.png" width="600"/ -->
<p/>

This product is meant for users who can type fast, and prefer typing over mouse/voice commands. Therefore, ==Command Line Interface (CLI) is the primary mode of input.== 

{{ embed_topic("project-constraints.md#constraint-cli", "Admin " + icon_embedding + " Project Contstraints → More info about the 'CLI app' requirement", "projectProduct-constraintCli", "2") }}
<p/>

</div>
{% endmacro %} 

{% from "common/macros.njk" import embed_topic with context %}
{% from "common/admin.njk" import show_admin_page with context %}
{{ show_admin_page("project-product", show_main_text) }}
