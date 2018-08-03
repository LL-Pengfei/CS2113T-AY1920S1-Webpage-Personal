<navbar placement="top" type="inverse">
  <a slot="brand" href="{{baseUrl}}/index.html" title="Home" class="navbar-brand">{{ module_pair }} <small>{{ period }}</small></a>
  <dropdown text="Nested" class="nav-link">
    <li><a href="{{baseUrl}}/index.html" class="dropdown-item"> {{ icon_tick }} Nested (current format)</a></li>
    <li><a href="{{baseUrl}}/index-flat.html" class="dropdown-item">&nbsp;&nbsp;&nbsp;&nbsp;Flat</a></li>
  </dropdown>
  <li><a href="{{baseUrl}}/index.html" class="nav-link"><md>**Schedule**</md></a></li>
  <li><a href="{{baseUrl}}/se-book-adapted/index.html" class="nav-link"><md>**Textbook**</md></a></li>
  <li><a href="{{baseUrl}}/admin/index.html" class="nav-link"><md>**Admin Info**</md></a></li>
  <dropdown text="Links" class="nav-link">
    <li><a href="{{module_org}}/website/issues" target="_blank" class="dropdown-item"> {{ fas_bug }} Report Bugs</a></li>
    <li><a href="{{slack_team}}" target="_blank" class="dropdown-item">{{ fab_slack_hash }} Slack</a></li>
    <li><a href="{{module_org}}/forum/issues" target="_blank" class="dropdown-item">{{ fas_comment }} Forum</a></li>
    <li><a href="{{ baseUrl }}/admin/instructors.html" class="dropdown-item">{{ fas_user_tie }} Instructors</a></li>
    <li><a href="{{ivle_announcements}}" target="_blank" class="dropdown-item">{{ glyphicon_bullhorn }} IVLE Announcements</a></li>
    <li><a href="{{ivle_files}}" target="_blank" class="dropdown-item">{{ fas_file_upload }} IVLE File Submissions</a></li>
    <li><a href="{{baseUrl}}/admin/tutorials.html" target="_blank" class="dropdown-item">{{ glyphicon_calendar }} Tutorial Schedule</a></li>
    <li><a href="{{team_IDs_page}}" target="_blank" class="dropdown-item">{{ glyphicon_list_alt }} Team IDs</a></li>
    <li><a href="{{java_coding_standard}}" target="_blank" class="dropdown-item">{{ fas_code }} Java Coding Standard</a></li>
    <li><a href="{{module_org}}/samplerepo-things" target="_blank" class="dropdown-item">{{ icon_repo }} samplerepo-things</a></li>
    <li><a href="{{module_org}}/addressbook-level1" target="_blank" class="dropdown-item">{{ icon_repo }} Addressbook-level1</a></li>
    <li><a href="{{module_org}}/addressbook-level2" target="_blank" class="dropdown-item">{{ icon_repo }} Addressbook-level2</a></li>
    <li><a href="{{module_org}}/addressbook-level3" target="_blank" class="dropdown-item">{{ icon_repo }} Addressbook-level3</a></li>
    <li><a href="{{module_org}}/addressbook-level4" target="_blank" class="dropdown-item">{{ icon_repo }} Addressbook-level4</a></li>
    <li><a href="{{baseUrl}}/admin/projectList.html" target="_blank" class="dropdown-item">{{ fas_th_list }} Projects List</a></li>
  </dropdown>
  <li slot="right" class="nav-link">
    <form class="navbar-form">
      <searchbar :data="searchData" placeholder="Search" :on-hit="searchCallback" menu-align-right ></searchbar>
    </form>
  </li>
</navbar>
