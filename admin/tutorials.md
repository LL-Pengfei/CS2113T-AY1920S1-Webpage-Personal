{% macro show_main_text() %}
<div id="main">

<panel type="seamless" expanded >
<span slot="header" class="card-title"><markdown>### Tutorial Timetable</markdown></span>
<div id="tutorialTimetable">

<tip-box> 

{{ icon_important_big_red }} **Our tutorial IDs are different from LumiNUS/Edurec.** <br> 
 Format: `CS2113T-W12` means CS2113T tutorial in the time slot `Wednesday` `1200-1300` and so on.

</tip-box>

| Module       | Tutorial ID |%%ID in LumiNUS%%<br>%%(not to be used)%%| Time             | Venue       | Tutors (<a href="{{ baseUrl }}/admin/instructors.html">contact details</a>)
|--------------|-------------|-----------------------------------------|------------------|-------------|-------------------
| **CS2113T**  | W12         |      %%(C01)%%                          | **W**ed **12**00 | COM1-B103   | TBD
| **CS2113T**  | W13         |      %%(C02)%%                          | **W**ed **13**00 | COM1-B103   | TBD 
| **CS2113T**  | W17         |      %%(C09)%%                          | **W**ed **17**00 | COM1-B103   | TBD
| **CS2113T**  | T09         |      %%(C05)%%                          | **T**hu **09**00 | COM1-B103   | TBD
| **CS2113T**  | T12         |      %%(C04)%%                          | **T**hu **12**00 | COM1-B103   | TBD
| _CS2113_     | T13         |      %%(1)%%                            | **T**hu **13**00 | COM1-B103   | TBD
| _CS2113_     | T14         |      %%(3)%%                            | **T**hu **14**00 | COM1-B103   | TBD
| _CS2113_     | T16         |      %%(2)%%                            | **T**hu **16**00 | COM1-B103   | TBD
| **CS2113T**  | F09         |      %%(C06)%%                          | **F**ri **09**00 | COM1-B103   | TBD
| **CS2113T**  | F10         |      %%(C03)%%                          | **F**ri **10**00 | COM1-B103   | TBD 
| **CS2113T**  | F11         |      %%(C08)%%                          | **F**ri **11**00 | COM1-B103   | TBD  
| **CS2113T**  | F14         |      %%(C07)%%                          | **F**ri **14**00 | COM1-B103   | TBD 

</div>
</panel>

<panel type="seamless" header="### Tutorial Structure" expanded >
<div id="tutorialStructure">

**What happens during the tutorial**:

* A tutorial group is handled by two tutors. Each tutor will work with two teams.
* The tutor will direct students to share/discuss evidence of learning the weekly topics.
* If some students have met with difficulties while learning a topic, the tutor can direct those students to get help from those who have learned the topic. **The number of topics that can be covered in the tutorial session depends on how well-prepared you are.**
* The tutor will observe, and give feedback on how well you are learning required topics.
* Please ==bring your laptop to tutorials.== You often need it to show evidence of learning the topics. At other times, we ask you to work on project related things with your team members, which too may require the laptop.

<div class="indented-level2">
{{ embed_topic("appendixC-faq.md#admin-faq-noLaptop", "Admin " + icon_embedding + " Appendix C(FAQ): What if I don't carry around a laptop?", "tutorials-faqLaptop", "4") }}
</div>

<br/>

**The role of our tutors** is different from tutors in other modules.

* **No direct tech help**: Tutors are prohibited from giving direct technical help. %%Rationale: We want you to learn the vital survival skill of troubleshooting technical problems.%%

<div class="indented-level2">
{{ embed_topic("appendixD-help.md#main", "Admin " + icon_embedding + " Appendix D: How to get Help in " + module_pair, "tutorials-apdxD", "2") }}
</div>

<br/>

* **No ‘teaching’**: Tutors are prohibited from “teaching” concepts that are covered in lectures or other learning resources given to you. Self-learning is a vital part of the module. But of course tutors can help you clarify doubts under the right circumstances.

<div class="indented-level2">
{{ embed_topic("appendixD-help.md#questions-for-tutros", "Admin " + icon_embedding + " Appendix D (extract): Questions suitable for tutor", "tutorials-apdxDtutorQuestions", "2") }}
</div>

<br/>

* **No leading from the front**: Tutors are not expected to lead your project effort. They will not tell you how to do project tasks or when to do project tasks. You have to figure those out yourselves. But tutors will give you feedback on how you are doing (or have done) project tasks so that you can improve further.   

**Timing/venue:**

* Please refer to the {{ schedule_link }} for further details on each tutorial.
* You are expected to arrive on time. ==Punctuality is considered for participation marks.==
* You may leave the class 15 minutes before the hour if you have another class right after. There is no need to wait till the tutor dismisses you. However, inform the tutor (as a courtesy) before leaving if you leave before the class is dismissed.
* Please make sure you ==vacate the table 5 minutes before the hour== so that the next group can start on time.
* In the past many students have suggested to increase the tutorial duration because 1 hour is barely enough to get through all weekly topics. Increasing the tutorial time is not possible due to lack of venues and tutors. Instead, let's try to make the best of the one hour available by coming well prepared and starting on time.

**Grading:**

Tutorials are not graded. However, your conduct will be reviewed by team members and the tutor which will determine your participation marks.

<div id="exchangeStudentTutorialSignup">

**[Exchange students only] Registering for tutorials:**

* Exchange students need to use the ORATUT system to register for the tutorials. You must have received the instructions from UG office on how/when to go about the registration process. If not, please talk to UG office. When we can see your appeal on ORATUT, we can allocate you to the tutorial slot.
</div>


</div>
</panel>
</div>
{% endmacro %}

{% from "common/macros.njk" import embed_topic with context %}
{% from "common/admin.njk" import show_admin_page with context %}
{{ show_admin_page("tutorials", show_main_text) }}
