{% from "schedule/index.md" import weeks, current_weeks with context %}
<header>
<navbar placement="top">
  <a slot="brand" href="{{baseUrl}}/index.html" title="Home" class="navbar-brand">{{ module_pair }} <small>{{ period }}</small></a>
  <dropdown text="Schedule" class="nav-link">
{% for week in weeks %}
<li><a href="{{ baseUrl }}/schedule/week{{ week.num }}/index.html" class="dropdown-item"> <md>**Week {{ week.num }}** [{{ week.day }}] {% if current_weeks[0] == week.num %} :fas-arrow-circle-left:{% endif %}</md></a></li>
{% endfor %}
  </dropdown>
  <li><a href="{{baseUrl}}/se-book-adapted/index.html" class="nav-link"><md>**Textbook**</md></a></li>
  <li><a href="{{baseUrl}}/admin/index.html" class="nav-link"><md>**Admin Info**</md></a></li>
  <dropdown text="Links" class="nav-link">
    <li><a href="{{bugs_link}}" target="_blank" class="dropdown-item"><md>:fas-bug:</md> Report Bugs</a></li>
    <li><a href="{{slack_team}}" target="_blank" class="dropdown-item"><md>:fab-slack-hash:</md> Slack</a></li>
    <li><a href="{{forum_link}}" target="_blank" class="dropdown-item"><md>:fas-comment:</md> Forum</a></li>
    <li><a href="{{baseUrl}}/admin/project-overview.html" class="dropdown-item">{{ icon_project }} Project Info</a></li>
    <li><a href="{{ baseUrl }}/admin/instructors.html" class="dropdown-item"><md>:fas-user-tie:</md> Instructors</a></li>
    <li><a href="{{ivle_announcements}}" target="_blank" class="dropdown-item"><md>:glyphicon-bullhorn:</md> Announcements</a></li>
    <li><a href="{{ivle_files}}" target="_blank" class="dropdown-item"><md>:fas-file-upload:</md> File Submissions</a></li>
    <li><a href="{{baseUrl}}/admin/tutorials.html" target="_blank" class="dropdown-item"><md>:glyphicon-calendar:</md> Tutorial Schedule</a></li>
    <li><a href="https://github.com/nusCS2113-AY1920S1/duke" target="_blank" class="dropdown-item"><md>:glyphicon-git:</md> Duke </a></li>
    <li><a href="{{java_coding_standard}}" target="_blank" class="dropdown-item"><md>:fas-code:</md> Java Coding Standard</a></li>
    <li><a href="{{module_org}}/samplerepo-things" target="_blank" class="dropdown-item">{{ icon_repo }} samplerepo-things</a></li>
    <li><a href="{{baseUrl}}/admin/projectList.html" class="dropdown-item"><md>:fas-th-list:</md> Projects List</a></li>
    <li><a href="{{baseUrl}}/admin/reposenseConfigTemplates.html" class="dropdown-item"><md>:fas-th-list:</md> config.json templates for Reposense</a></li>
    <li><a href="https://nus{{ module | lower }}-{{ semester | lower }}.github.io/dashboard-beta" target="_blank" class="dropdown-item"><md>:fas-chart-area:</md> Project Code Dashboard (BETA)</a></li>
    <li><a href="https://repl.it/classroom/invite/cuFCDgh" target="_blank" class="dropdown-item"><md>:glyphicon-blackboard:</md> Repl.it classroom</a></li>
  </dropdown>
  <li slot="right" class="nav-link">
    <form class="navbar-form">
      <searchbar :data="searchData" placeholder="Search" :on-hit="searchCallback" menu-align-right ></searchbar>
    </form>
  </li>
</navbar>
</header>
