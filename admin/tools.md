{% macro show_main_text() %}
<div id="main">

<img src="{{baseUrl}}/admin/images/toolsList.png" style="width: 700px"><br>

**Learning Management System**: This module website is the main source of information for the module. In addition, we use LumiNUS for lecture webcasts and for admin matters %%(e.g., announcements, file submissions, grade book, ...)%%.

<div id="github">

**Collaboration platform**: You are ==_required to_ use GitHub== as the hosting and collaboration platform of your project (i.e., to hold the Code repository, Issue Tracker, etc.). See [Appendix E]({{baseUrl}}/admin/index.html#admin-appendixE-github) for more info on how to setup and use GitHub for your project.

<box>

**Create a GitHub account** (if you don't have one yet), as explained in the panel below.

{{ embed_topic("appendixE-gitHub.md#githubAccount", "Admin " + icon_embedding + " **Appendix E - GitHub: Creating an Account**", "-", "2") }}

</box>

See [Appendix E - Using GitHub](appendixE-gitHub.html) for more information.

</div>


<div id="rcs">

**Revision control**: You are ==_required to_ use Git==. Other revision control software are not allowed.  
The recommended GUI client for Git is [SourceTree](https://www.sourcetreeapp.com/) (which comes bundled with Git), but you may use any other, or none.

<box>

**Install Git and a Git GUI client** on your computer.<br>
  {{ icon_tip }} SourceTree comes with bundled with Git i.e., if you install SourceTree, you get both Git and a GUI client in one shot.

<div id="git-username">

**Set Git `user.name`**: We use various tools to analyze your code. For us to be able to identify your commits, we encourage you to ==set your Git `user.name` in all computers you use== to a sensible string that uniquely identify you. ==You can to GitHub username or as your Git username==. If this user name is not set properly or if you use multiple user names for Git, our tools might miss some of your work and as a result you might not get credit for some of your work.

After installing Git in a computer, you can set the Git username as follows:
1. Open a command window that can run Git commands (e.g., Git bash window)
2. Run the command `git config --global user.name YOUR_GITHUB_USERNAME` (omit the `--global` flag to limit the setting to the current repo repo)<br>
   e.g., `git config --global user.name JohnDoe` or from within the repo `git config user.name JohnDoe`

More info about setting Git username is [here](https://help.github.com/articles/setting-your-username-in-git/).

</box>

</div>

<div id="communication">

**Communication**: Keeping a record of communications among your team can help you, and us, in many ways. We encourage you to do at least some of the project communication in written medium (e.g., GitHub Issue Tracker) to practice how to communicate technical things in written form.
 * We encourage you to ==post your questions/suggestions in this [github/nus{{ module }}-{{ semester }}/forum]({{module_org}}/forum/issues)==.
 * You can use our slack channel [{{slack_team}}]({{slack_team}}) for team communications. You need to ==join the slack channel== (you'll need to use an email address ending in `@nus.edu.sg`, `@comp.nus.edu.sg` or `@u.nus.edu`) to start using this channel).
   * Note that slack is useful for quick chats while issue tracker is useful for longer-running conversations.
   * All official communications from the teaching team will happen via the [github/nus{{ module }}-{{ semester }}/forum]({{module_org}}/forum/issues); the same will be linked to in LumiNUS announcements.
 * You are encouraged to use channels with a wider audience (i.e., the GitHub issue tracker) for module-related communication as much as possible, rather than private channels such as private slack/FB messages or direct emails. %%Rationale: more classmates can benefit from the discussions%%.

</div>


**IDE**: You are recommended to use [Intellij IDEA](https://www.jetbrains.com/idea/) for module-related programming work. You may use the community edition (free) or the ultimate edition (free for students). While the use of Intellij is not compulsory, note that module materials are optimized for Intellij. Use other IDEs at your own risk. 


**Analyzing code authorship**: We use a custom-built tool called [RepoSense](https://github.com/reposense/RepoSense) for extracting code written by each person.

<include src="reposenseCompatibility.md#main" />

</div>
{% endmacro %}

{% from "common/macros.njk" import embed_topic with context %}
{% from "common/admin.njk" import show_admin_page with context %}
{{ show_admin_page("tools", show_main_text) }}
