{% macro show_main_text() %}
<div id="main">

<!--
[<img src="{{baseUrl}}/admin/images/timeline.png" width="100%">](images/timeline.png)

To expedite your project implementation, you will be given some sample code (AddressBook-Level1 to AddressBook-Level4, shown as `AB1` to `AB4` in the diagram above).  You can use `AB1` to `AB3` to ramp up your tech skills in preparation for the project. `AB4` is the version you will use as the starting point for your final project. Some of the work you do in `AB1` to `AB3` can be ported over to `AB4` and can be used to claim credit in the final project.
-->

Given below is the ==tentative high-level timeline== of the project. <br> %%This is subject to change. Please follow the weekly project tabs for updated instructions.%%

Week  | Stage     | Activities
------|-----------|-----------
**2** |warmup    | <span id="warmup-overview">Set up prerequisites. Get started on Duke</span>
**3** |inception| <span id="inception-overview">Continue Phase 1. Decide on a overall project direction %%(user profile, problem addressed, societal impact, optimize or morph?).%%</span>
**4** |mid-v1.0 | <span id="mid-v10-overview">Move towards completing Phase 1 of the project. Achieve some team tasks </span>
**5** |v1.0     | <span id="v10-overview">Decide on requirements %%(user stories, use cases, non-functional requirements).%%</span>
**6** |mid-v1.1 | <span id="mid-v11-overview">Conceptualize product and document it as a user guide(draft), draft a rough project plan.</span>
**7** |v1.1     | <span id="v11-overview">Set up Phase 2 project repo and start moving documents and code to it. Do local-impact changes to the code base. Submit UG for review.</span>
**8** |mid-v1.2 | <span id="mid-v12-overview">Attempt to do global-impact changes to the code base. Adjust project schedule/rigor as needed, start proper milestone management.</span>
**9** |v1.2     | <span id="v12-overview">Update UG if necessary. Move code towards v2.0 in small steps, start documenting design/implementation details in DG.</span>
**10**|mid-v1.3 | <span id="mid-v13-overview">Complete a draft of the DG and seek feedback from your tutor. Continue to enhance features. Make code RepoSense-compatible. Try doing a proper release.</span>
**11**|v1.3     | <span id="v13-overview">Release as a jar file, release updated user guide, peer-test released products, verify code authorship. Seek code quality comments from your tutor</span>
**12**|mid-v1.4 | <span id="mid-v14-overview">Tweak as per peer-testing results, draft Project Portfolio Page, practice product demo.</span>
**13**|v1.4     | <span id="v14-overview">Final tweaks to docs/product, release product, demo product, evaluate peer projects.</span>

More details of each stage is provided elsewhere is this website.

</div>
{% endmacro %}

{% from "common/admin.njk" import show_admin_page with context %}
{{ show_admin_page("project-timeline", show_main_text) }}
