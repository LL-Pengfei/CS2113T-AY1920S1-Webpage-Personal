{% macro show_main_text() %}
<div id="main">

If your team is facing difficulties due to differences in skill/motivation /availability among team members,

* **First, do not expect everyone to have the same skill/motivation level as you.** It is fine if someone wants to do less and have low expectations from the module. That doesn't mean that person is a bad person. Everyone is entitled to have their own priorities.

* **Second, don't give up.** It is unfortunate that your team ended up in this situation, but you can turn it into a good learning opportunity. You don't get an opportunity to save a sinking team every day :-)

* **Third, if you care about your grade and willing to work for it, you need to take initiative** to turn the situation around or else the whole team is going to suffer. Don't hesitate to take charge if the situation calls for it. By doing so, you'll be doing a favor for your team. Be professional, kind, and courteous to the team members, but also be firm and assertive. It is your grade that is at stake. Don't worry about making a bad situation worse. You won't know until you try.

* **Finally, don't feel angry or 'wronged'.** Teamwork problems are not uncommon in this module and we know how to grade so that you will not be penalized for others' low contribution. We can use Git to find exactly what others did. It's not your responsibility to get others to contribute.

Given below are some suggestions you can adopt if the project work is not going smooth due to team issues. Note that the below measures can result in some team members doing more work than others and earning better project grades than others. It is still better than sinking the whole team together.

* **Redistribute the work**: Stronger programmers in the team should take over the critical parts of the code.

* **Enforce stricter integration workflow**: Appoint an integrator (typically, the strongest programmer). His/her job is to maintain the integrated version of the code. He/she should not accept any code that breaks the existing product or is not up to the acceptable quality standard. It is up to others to submit acceptable code to the integrator. Note that if the integrator rejected your code unreasonably, you can still earn marks for that code. You are allowed to submit such 'rejected' code for grading. They can earn marks based on the quality of the code.

**If you have very unreliable or totally disengaged team members** :

* Re-allocate to others any mission-critical work allocated to that person so that such team members cannot bring down the entire team.
* However, do not leave out such team members from project communications. Always keep them in the loop so that they can contribute any time they wish to.
* Furthermore, evaluate them sincerely and fairly during peer evaluations so that they do get the grade their work deserves, no more, no less.
* Be courteous to such team members too. Some folks have genuine problems that prevent them from contributing more although they may not be able tell you the reasons. Just do your best for the project and assume everyone else is doing their best too, although their best may be lower than yours.

</div>
{% endmacro %}

{% from "common/admin.njk" import show_admin_page with context %}
{{ show_admin_page("appendixF-teamworkIssues", show_main_text) }}