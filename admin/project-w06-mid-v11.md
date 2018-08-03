{% macro show_main_text() %}
<div id="main">

<div id="title">

</div>
<div id="body">

<tip-box>

Overview: <include src="project-timeline.md#mid-v11-overview" inline />
</tip-box>

<div id="product">

**<big>Project Management:</big>**

* One team member: <trigger trigger="click" for="modal:v10-setuporg">Set up the team org</trigger> and <trigger trigger="click" for="modal:v10-setuprepo">team repo</trigger> for your team if you haven't done that already.
  * Set up [auto-publishing of docs](https://nus-{{ module | lower }}-{{ semester | lower }}.github.io/addressbook-level4/UsingTravis.html#enabling-auto-publishing-of-documentation)

<modal large title="Admin {{ icon_embedding }} Appendix E: Using GitHub Project Hosting → Organization Setup" id="modal:v10-setuporg">
  <include src="appendixE-gitHub.md#organization-setup"/>
</modal>
<modal large title="Admin {{ icon_embedding }} Appendix E: Using GitHub Project Hosting → Repo Setup" id="modal:v10-setuprepo">
  <include src="appendixE-gitHub.md#repo-setup"/>
</modal>

* All members: Set up your own forks of the team repo, so that you can submit PRs to your team repo using the forking workflow.

<tip-box type="important"> 
  
Before you do any coding for the project, please ensure you have set the Git username correctly (see panel below for more details) in all Computers you use for coding.

<panel src="appendixE-gitHub.md#git-username" header="%%Admin {{ icon_embedding }} Appendix E → Setting Git Username to Match GitHub Username%%" />

</tip-box>

</div>
<div id="documentation">

**<big>Documentation:</big>** 

<tip-box>

**Recommended procedure for updating docs**:

1. Divide among yourselves who will update which parts of the document(s).
1. Update the team repo by following the <trigger trigger="click" for="modal:v10-forkingworkflow">forking workflow</trigger>.
1. One member: create a PR from your ==team repo `master` branch== to [[nus-{{ module | lower }}-{{ semester }}/addressbook-level4]({{module_org}}/addressbook-level4)] `master` branch. PR name: `[v1.x][Team ID] Product Name` e.g., `[v1.x][T09-B2] Contact List Pro`. %%&nbsp;As you merge code to your team repo's `master` branch, this PR will auto-update to reflect how much your team's product has progressed (that's why we use `v1.x` instead of `v1.0` in the PR title).%% In the PR description <tooltip content="use @githubUserName">mention</tooltip> the other team members so that they get notified when the tutor adds comments to the PR.

<modal large title="TextBook {{ icon_embedding }}" id="modal:v10-forkingworkflow">
  <include src="../book/revisionControl/forkingWorkflow/unit-inElsewhere-asFlat.md" boilerplate/>
</modal>

</tip-box>

<div class="indented">

  Update the following pages in your project repo:
</div> 
 
* **About Us page**:  
  This page is used for module admin purposes. ==Please follow the format closely to avoid penalties==. 
  * Replace info of SE-EDU developers with info of your team, including a ==suitable photo== as described <trigger trigger="click" for="modal:mid-v12-photo">here</trigger>.  
  * Including the name/photo of the supervisor/lecturer is optional. 
  * The photo of a team member should be `doc/images/githbub_username_in_lower_case.png` %%e.g. `docs/images/damithc.png`%%.

<modal large title="Admin {{ icon_embedding }} Choosing a profile photo" id="modal:mid-v12-photo">
  <include src="project-deliverables.md#profile-photo"/>
</modal>

  * Indicate the different roles played and responsibilities held by each team member. You can reassign these roles and responsibilities later in the project, if necessary.  

<div class="indented-level2">
<panel src="project-scope.md#roles" header="Admin {{ icon_embedding }} Project Scope (extract): roles and responsibilities" class="embedding" minimized />
</div>
<p/>

* **README.adoc** page: Update it to match your project. 
  * Add a UI mockup of your intended final product.   
    Note that the ==image of the UI should be `docs/images/Ui.png`== so that it can be downloaded by our scripts.  
  * The original `README.adoc` file (which doubles as the landing page of your project website) is written to read like the introduction to an SE learning/teaching resource. You should ==restructure this page to look like the home page of a real product== (not a school project) targeting real users %%&nbsp;e.g. remove references to addressbook-level3, Learning Outcomes etc. mention target users, add a marketing blurb etc.%% On a related note, also remove `Learning Outcomes` link and related pages.
  * Acknowledge the original source of the code i.e. AddressBook-Level4 project created by SE-EDU initiative at `https://github.com/se-edu/`

* **User Guide**: Start moving the content from your User Guide (draft created in previous weeks) into the User Guide page in your repository.

* **Developer Guide**: Similar to the User Guide, start moving the content from your Developer Guide (draft created in previous weeks) into the Developer Guide page in your team repository.

**<big>Product:</big>**

* Each member can attempt to do a <tooltip content="a change impacting only one component">local-impact</tooltip> change to the code base.

  **Objective**: To familiarize yourself with at least one component the code.

  **Description**: Divide the <tooltip content="components as stated in the [Developer Guide: Architecture]">components</tooltip> among yourselves. Each member can do some small enhancements to their component(s) to learn the code of that component. Some suggested enhancements are given in the [AddressBook-Level4 developer guide](https://nus-{{ module | lower }}-{{ semester }}.github.io/addressbook-level4/DeveloperGuide.html#improving-each-component).

  **Submission**: Create PRs from your own fork to your team repo. Get it merged by following your team's workflow.
  
  :exclamation: Before you start coding, please read our reuse policy given below, in particular, ==how to give credit when you reuse code from Internet or classmates==:

<div class="indented-level2">
<panel src="appendixB-policies.md#policy-reuse" header="Admin {{ icon_embedding }} Appendix B: Policies → Policy on Reuse" class="embedding" minimized /><p/>
</div>


</div>

</div>
</div>
{% endmacro %}

{% from "common/admin.njk" import show_admin_page with context %}
{{ show_admin_page("project-w06-mid-v11", show_main_text) }}