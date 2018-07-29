<frontmatter>
title: "Full Schedule of Module Activities"
footer: footer.md
</frontmatter>

{% import "common/outcomes.njk" as outcomes with context %}

{% set weeks = [
    {num: "1", day:"Aug 13"},
    {num: "2", day:"Aug 20"},
    {num: "3", day:"Aug 27"}, 
    {num: "4", day:"Sep 3"},
    {num: "5", day: "Sep 10" },
    {num: "6", day: "Sep 17" }
] %}


{% set current_weeks = ["1","2"] %}


{% set all_outcomes = [
{week: "2"},
  {name: "SE Intro"},
    {heading: "Can explain pros and cons of software engineering"},
      {location: ["softwareEngineering", "introduction", "prosAndCons"]},
  {name: "Revision Control"},
    {heading: "Can use Git to save history"},
      {location: ["revisionControl", "what"]},
      {location: ["revisionControl", "repositories"]},
      {location: ["gitAndGithub", "init"]},
      {location: ["revisionControl", "savingHistory"]},
      {location: ["gitAndGithub", "commit"], omit_evidence: true},
      {location: ["gitAndGithub", "ignore"]},
    {heading: "Can communicate with a remote repo"},
      {location: ["revisionControl", "remoteRepositories"], omit_evidence: true},
      {location: ["gitAndGithub", "clone"]},
      {location: ["gitAndGithub", "pull"]},
      {location: ["gitAndGithub", "push"]},
    {heading: "Can traverse Git history"},
      {location: ["revisionControl", "usingHistory"], omit_evidence: true},
      {location: ["gitAndGithub", "checkout"]},
      {location: ["gitAndGithub", "tag"]},
      {location: ["gitAndGithub", "stash"]},
  {name: "Design"},
    {heading: "Can explain models"},
      {location: ["modeling", "introduction", "what"], omit_evidence: true},
      {location: ["modeling", "introduction", "how"]},
    {heading: "Can explain OOP"},
      {location: ["oop", "introduction", "what"], omit_evidence: true},
      {location: ["oop", "objects", "what"]},
      {location: ["oop", "classes", "what"]},
      {location: ["oop", "objects", "abstraction"], omit_evidence: true},
      {location: ["oop", "objects", "encapsulation"], omit_evidence: true},
    {heading: "Can explain basic object/class structures"},
      {location: ["modeling", "modelingStructures", "ooStructures"], omit_evidence: true},
      {location: ["modeling", "modelingStructures", "classDiagramsBasic"]},
      {location: ["uml", "miscellaneous", "objectVsClassDiagrams"], omit_evidence: true},
{week: "3"},
  {name: "Testing"},
    {heading: "Can automate simple regression testing of text UIs"},
      {location: ["testing", "introduction", "what"]},
      {location: ["testing", "testingTypes", "regressionTesting", "what"]},
      {location: ["testing", "testAutomation", "what"], omit_evidence: true},
      {location: ["testing", "testAutomation", "testingTextUis"]},
  {name: "IDEs"},
    {heading: "Can use basic features of an IDE"},
      {location: ["ides", "introduction", "what"]},
      {location: ["intellij", "projectSetup"]},
      {location: ["intellij", "codeNavigation"]},
    {heading: "Can use intermediate level features of an IDE"},
      {location: ["ides", "debugging", "what"], omit_evidence: true},
      {location: ["intellij", "debuggingBasic"]},
      {location: ["intellij", "productivityShortcuts"]},
  {name: "Refactoring"},
    {heading: "Can refactor code at a basic level"},
      {location: ["refactoring", "what"]},
      {location: ["intellij", "refactoring"]},
      {location: ["refactoring", "how"]},
      {location: ["refactoring", "when"]},
  {name: "Implementation"},
    {heading: "Can use Java varargs feature"},
      {location: ["javaTools", "varargs"]},
    {heading: "Can use Java Collections"},
      {location: ["javaTools", "collections"]},
    {heading: "Can use Java enumerations"},
      {location: ["oop", "classes", "enumerations"]},
      {location: ["javaTools", "enums"]},
    {heading: "Can implement class-level members"},
      {location: ["oop", "classes", "classLevelMembers"], omit_evidence: true},
      {location: ["oop", "inheritance", "overloading"], omit_evidence: true},
  {name: ":parking: Project"},
    {heading: "Can define the target of a product", priority: "1", file: "project.md#inception"},
    {heading: "Can work with a 1KLoC code base", priority: "1", file: "project.md#1kloc"},
{week: "4"},
  {name: "Requirements"},
    {heading: "Can explain requirements"},
      {location: ["requirements", "introduction"], omit_evidence: true},
      {location: ["requirements", "nonFunctionalRequirements"], omit_evidence: true},
      {location: ["requirements", "prioritizing"], omit_evidence: true},
      {location: ["requirements", "quality"], omit_evidence: true},
    {heading: "Can explain some techniques for gathering requirements"},
      {location: ["gatheringRequirements", "brainstorming"], omit_evidence: true},
      {location: ["gatheringRequirements", "productSurveys"], omit_evidence: true},
      {location: ["gatheringRequirements", "observation"], omit_evidence: true},
      {location: ["gatheringRequirements", "userSurveys"], omit_evidence: true},
      {location: ["gatheringRequirements", "interviews"], omit_evidence: true},
      {location: ["gatheringRequirements", "focusGroups"], omit_evidence: true},
      {location: ["gatheringRequirements", "prototyping"], omit_evidence: true},
    {heading: "Can use some techniques for specifying requirements"},
      {subheading: "Prose"},
        {location: ["specifyingRequirements", "prose", "what"], omit_evidence: true},
      {subheading: "Feature Lists"},
        {location: ["specifyingRequirements", "featureList", "what"], omit_evidence: true},
      {subheading: "User Stories"},
        {location: ["specifyingRequirements", "userStories", "introduction"]},
        {location: ["specifyingRequirements", "userStories", "details"], omit_evidence: true},
        {location: ["specifyingRequirements", "userStories", "usage"]},
      {subheading: "Use Cases"},
        {location: ["specifyingRequirements", "useCases", "introduction"], omit_evidence: true},
        {location: ["specifyingRequirements", "useCases", "identifying"], omit_evidence: true},
        {location: ["specifyingRequirements", "useCases", "details"]},
        {location: ["specifyingRequirements", "useCases", "usage"], omit_evidence: true},
      {subheading: "Glossary"},
        {location: ["specifyingRequirements", "glossary", "what"], omit_evidence: true},
      {subheading: "Supplementary Requirements"},
        {location: ["specifyingRequirements", "supplementaryRequirements", "what"], omit_evidence: true},
  {name: "Documentation"},
    {heading: "Can use some common documentation tools"},
      {subheading: "Javadoc"},
        {location: ["documentation", "tools", "javaDoc", "what"], omit_evidence: true},
        {location: ["documentation", "tools", "javaDoc", "how"], omit_evidence: true},
      {subheading: "Markdown"},
        {location: ["documentation", "tools", "markdown", "what"], omit_evidence: true},
        {location: ["documentation", "tools", "markdown", "how"], omit_evidence: true},
      {subheading: "AsciiDoc"},
        {location: ["documentation", "tools", "asciiDoc", "what"], omit_evidence: true},
  {name: "Implementation"},
    {heading: "Can implement classes"},
    {heading: "Can do exception handling in code"},
      {location: ["errorHandling", "introduction", "what"], omit_evidence: true},
      {location: ["errorHandling", "exceptions", "what"], omit_evidence: true},
      {location: ["errorHandling", "exceptions", "how"]},
      {location: ["errorHandling", "exceptions", "when"], omit_evidence: true},
  {name: "Project Management"},
    {heading: "Can create PRs on GitHub"},
      {location: ["revisionControl", "branching"]},
      {location: ["gitAndGithub", "branch"]},
      {location: ["gitAndGithub", "createPRs"]},
  {name: ":parking: Project"},
    {heading: "Can define requirements of a product", priority: "1", file: "project.md#v10"},
{week: "5"},
  {name: "Design"},
    {heading: "Can explain single responsibility principle"},
      {location: ["principles", "singleResponsibilityPrinciple"]},
  {name: "Implementation"},
    {heading: "Can implement inheritance"},
      {location: ["oop", "inheritance", "what"], omit_evidence: true},
    {heading: "Can implement overloading"},
    {heading: "Can implement polymorphism"},
      {subheading: "Method Overriding"},
        {location: ["oop", "inheritance", "overriding"], omit_evidence: true},
      {subheading: "Polymorphism"},
        {location: ["oop", "polymorphism", "what"], omit_evidence: true},
      {subheading: "Abstract Classes"},
        {location: ["oop", "inheritance", "abstractClasses"], omit_evidence: true},
      {subheading: "Interfaces"},
        {location: ["oop", "inheritance", "interfaces"], omit_evidence: true},
  {name: "Quality Assurance"},
    {heading: "Can use simple JUnit tests"},
      {location: ["testing", "testingTypes", "developerTesting", "what"], omit_evidence: true},
      {location: ["testing", "testingTypes", "developerTesting", "why"]},
      {location: ["testing", "testAutomation", "usingTestDrivers"], omit_evidence: true},
      {location: ["testing", "testAutomation", "tools"], omit_evidence: true},
      {location: ["junit", "basic"]},
  {name: "Project Management"},
    {heading: "Can use GitHub PRs in a workflow"},
      {location: ["gitAndGithub", "mergeConflicts"]},
      {location: ["gitAndGithub", "managePRs"]},
    {heading: "Can follow Forking Workflow"},
      {location: ["revisionControl", "forkingWorkflow"], omit_evidence: true},
      {location: ["gitAndGithub", "forkingWorkflow"]},
      {location: ["revisionControl", "drcsVsCrcs"], omit_evidence: true},
      {location: ["revisionControl", "featureBranchFlow"], omit_evidence: true},
      {location: ["revisionControl", "centralizedFlow"], omit_evidence: true},
  {name: ":parking: Project"},
    {heading: "Can work with a 2KLoC code base", priority: "1", file: "project.md#2kloc"},
    {heading: "Can conceptualize a product", priority: "1", file: "project.md#v10"},
{week: "6"},
  {name: "Design"},
    {heading: "Can interpret an architecture diagram"},
      {location: ["design", "introduction", "what"], omit_evidence: true},
      {location: ["architecture", "architectureDiagrams", "reading"], omit_evidence: true},
      {location: ["designApproaches", "multilevelDesign", "what"]},
    {heading: "Can use intermediate-level class diagrams"},
      {location: ["uml", "classDiagrams", "dependencies", "what"], omit_evidence: true},
      {location: ["uml", "notes", "notes"], omit_evidence: true},
      {location: ["uml", "notes", "constraints"], omit_evidence: true},
      {location: ["uml", "classDiagrams", "associationsAsAttributes", "what"], omit_evidence: true},
      {location: ["modeling", "modelingStructures", "classDiagramsIntermediate"], omit_evidence: true},
    {heading: "Can interpret basic sequence diagrams"},
      {location: ["uml", "sequenceDiagrams", "introduction"], omit_evidence: true},
      {location: ["uml", "sequenceDiagrams", "basic"], omit_evidence: true},
      {location: ["uml", "sequenceDiagrams", "loops"], omit_evidence: true},
      {location: ["uml", "sequenceDiagrams", "objectCreation"], omit_evidence: true},
      {location: ["uml", "sequenceDiagrams", "minimalNotation"], omit_evidence: true},
      {location: ["modeling", "modelingBehaviors", "sequenceDiagramsBasic"]},
  {name: "Implementation"},
    {heading: "Can implement composition"},
      {location: ["oop", "associations", "composition"], omit_evidence: true},
    {heading: "Can implement aggregation"},
      {location: ["oop", "associations", "aggregation"], omit_evidence: true},
    {heading: "Can use logging"},
      {location: ["errorHandling", "logging", "what"], omit_evidence: true},
      {location: ["errorHandling", "logging", "how"]},
    {heading: "Can use assertions"},
      {location: ["errorHandling", "assertions", "what"], omit_evidence: true},
      {location: ["errorHandling", "assertions", "how"]},
      {location: ["errorHandling", "assertions", "when"]},
    {heading: "Can use Java8 streams"},
      {location: ["javaTools", "streamsBasic"]},
    {heading: "Can use JavaFX to build a simple GUI"},
      {location: ["javaTools", "javaFXBasic"]},
  {name: "Project Management"},
    {heading: "Can explain continuous integration and continuous deployment"},
      {location: ["integration", "introduction", "what"], omit_evidence: true},
      {location: ["integration", "buildAutomation", "what"]},
      {location: ["integration", "buildAutomation", "continuousIntegrationDeployment"]},
  {name: ":parking: Project"},
    {heading: "Can contribute to project documentation", priority: "1", file: "project.md#mid-v11"}
]%}


{% macro show_week_outcomes(week_num, path="") %}
<panel type="seamless" popup-url="{{baseUrl}}/schedule/week{{ week_num }}/outcomes.html" expanded no-close>
  <span slot="header" class="card-title activity-type">{{ icon_outcome }} Outcomes</span>
  <div class="indented">
  {{ outcomes.show_week_schedule_main(week_num, all_outcomes, path) }}
  </div>
</panel>
{% endmacro %}


{% macro show_week_todos(week_num, path="") %}
<panel type="seamless" expanded no-close>
  <span slot="header" class="card-title activity-type">{{ icon_todo }} Todo</span>
  <div class="indented">
  <include src="{{ path }}todo.md" />
  </div>
</panel>
{% endmacro %}


{% macro show_week_tutorial(week_num, path="") %}
<panel type="seamless" expanded no-close>
<span slot="header" class="card-title activity-type">{{ icon_tutorial }} Tutorial {{ week_num }}</span>
   <div class="indented">
   <include src="{{ path }}tutorial.md" />
   </div>
</panel>
{% endmacro %}


{% macro show_week_lecture(week_num, path="") %}
<panel type="seamless" expanded no-close>
<span slot="header" class="card-title activity-type">{{ icon_lecture }} Lecture {{ week_num }}</span>
  <div class="indented">
  <include src="{{ path }}lecture.md" />
  </div>
</panel>
{% endmacro %}


{% macro show_week_schedule(week_num, path="") %}
{{ show_week_todos(week_num, path) }}

{# omit outcomes if it is the first week #}
{% if week_num != "1" %} 
  {{ show_week_outcomes(week_num, path) }}
{% endif %}

{{ show_week_tutorial(week_num, path) }}
{{ show_week_lecture(week_num, path) }}

{% endmacro %}


{% macro show_past_week(week) %}
<panel type="seamless" src="week{{ week.num }}/index.md" no-close>
<span slot="header" class="card-title week-past"> Week {{ week.num }} [{{ week.day }}]</span>
</panel>
{% endmacro %}


{% macro show_future_week(week) %}
<panel type="seamless" src="week{{ week.num }}/index.md" no-close>
<span slot="header" class="card-title week-future"> Week {{ week.num }} [{{ week.day }}]</span>
</panel>
{% endmacro %}


{% macro show_current_week(week) %}
<panel type="seamless" expanded no-close>
<span slot="header" class="card-title week"> Week {{ week.num }} [{{ week.day }}]</span>
  {{ show_week_schedule(week.num, "week" + week.num + "/") }}
</panel>
{% endmacro %}

<!-- ============================= page content ============================================ -->

<link rel="stylesheet" href="{{baseUrl}}/css/main.css">
<link rel="stylesheet" href="{{baseUrl}}/css/schedule.css">

<include src="../common/header.md" />

<div class="website-content" id="main">

# Full Schedule of Module Activities

<panel src="overview/index.md" header=":exclamation: **Info relevant to all weeks**"  />
<panel src="../admin/tutorials.md#tutorialTimetable" header="**{{glyphicon_calendar}} Tutorial Timetable**" />

<p/>

{% for week in weeks %}
{% set current_week_num = current_weeks[0] | int %}
{% set week_num = week.num | int %}
{% if week.num in current_weeks %} 
  {{ show_current_week(week) }}
{% elseif week_num < current_week_num %}
  {{ show_past_week(week) }}
{% else %}
  {{ show_future_week(week) }}
{% endif %}
{% endfor %}


</div>