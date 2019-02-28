<frontmatter>
title: "Full Schedule of Module Activities"
footer: footer.md
head: scheduleHead.md
</frontmatter>

{% import "common/outcomes.njk" as outcomes with context %}

{% set weeks = [
    {num: "1", day:"Jan 14"},
    {num: "2", day:"Jan 21"},
    {num: "3", day:"Jan 28"},
    {num: "4", day:"Feb 4"},
    {num: "5", day: "Feb 11" },
    {num: "6", day: "Feb 18" },
    {num: "7", day: "Mar 4" },
    {num: "8", day: "Mar 11" },
    {num: "9", day: "Mar 18" },
    {num: "10", day: "Mar 25" },
    {num: "11", day: "Apr 1" },
    {num: "12", day: "Apr 8" },
    {num: "13", day: "Apr 12" }
] %}


{% set current_weeks = ["7"] %}


{% set all_outcomes = [
{week: "2"},
  {name: "SE Intro"},
    {heading: "SE Intro"},
      {location: ["softwareEngineering", "introduction", "prosAndCons"]},
  {name: "Revision Control"},
    {heading: "RCS: Basics & Git history"},
      {location: ["revisionControl", "what"]},
      {location: ["revisionControl", "repositories"]},
      {location: ["gitAndGithub", "init"]},
      {location: ["revisionControl", "savingHistory"]},
      {location: ["gitAndGithub", "commit"], omit_evidence: true},
      {location: ["gitAndGithub", "ignore"]},
      {location: ["revisionControl", "usingHistory"], omit_evidence: true},
      {location: ["gitAndGithub", "checkout"]},
      {location: ["gitAndGithub", "tag"]},
      {location: ["gitAndGithub", "stash"]},
    {heading: "RCS: Communicating with a remote repo"},
      {location: ["revisionControl", "remoteRepositories"], omit_evidence: true},
      {location: ["gitAndGithub", "clone"]},
      {location: ["gitAndGithub", "pull"]},
      {location: ["gitAndGithub", "push"]},
  {name: "Tools: IDEs"},
    {heading: "IDEs: Basic features"},
      {location: ["ides", "introduction", "what"]},
      {location: ["intellij", "projectSetup"]},
      {location: ["intellij", "codeNavigation"]},
    {heading: "IDEs: Intermediate features"},
      {location: ["ides", "debugging", "what"], omit_evidence: true},
      {location: ["intellij", "debuggingBasic"]},
      {location: ["intellij", "productivityShortcuts"]},
  {name: "OOP"},
    {heading: "OOP: Classes & Objects"},
      {location: ["oop", "introduction", "what"], omit_evidence: true},
      {location: ["oop", "objects", "what"], omit_evidence: true},
      {location: ["oop", "classes", "what"], omit_evidence: true},
      {location: ["oop", "objects", "abstraction"], omit_evidence: true},
      {location: ["oop", "objects", "encapsulation"], omit_evidence: true},
      {location: ["cppToJava", "classes", "definingClasses"]},
      {location: ["cppToJava", "classes", "gettersAndSetters"]},
      {location: ["oop", "classes", "classLevelMembers"], omit_evidence: true},
      {location: ["cppToJava", "classes", "classLevelMembers"], omit_evidence: true},
      {location: ["oop", "classes", "enumerations"]},
      {location: ["cppToJava", "misc", "enums"]},
{week: "3"},
  {name: "OOP"},
    {heading: "OOP: Inheritance"},
      {location: ["oop", "inheritance", "what"], omit_evidence: true},
      {location: ["uml", "classDiagrams", "classInheritance", "what"], omit_evidence: true},
      {location: ["oop", "inheritance", "overloading"], omit_evidence: true},
      {location: ["cppToJava", "inheritance", "basic"], omit_evidence: true},
  {name: "Tools: IDEs"},
    {heading: "IDEs: Basic refactoring"},
      {location: ["refactoring", "what"]},
      {location: ["intellij", "refactoring"]},
      {location: ["refactoring", "how"]},
      {location: ["refactoring", "when"]},
  {name: "Implementation"},
    {heading: "C++ to Java"},
      {location: ["cppToJava", "javaWorld", "what"], omit_evidence: true},
      {location: ["cppToJava", "javaWorld", "how"], omit_evidence: true},
      {location: ["cppToJava", "javaWorld", "editions"], omit_evidence: true},
    {heading: "Java classes"},
      {subheading: "Classes"},
      {location: ["cppToJava", "classes", "definingClasses"], omit_evidence: true},
      {location: ["cppToJava", "classes", "gettersAndSetters"], omit_evidence: true},
    {subheading: "Class-level members"},
      {location: ["oop", "classes", "classLevelMembers"], omit_evidence: true},
      {location: ["cppToJava", "classes", "classLevelMembers"], omit_evidence: true},
    {heading: "Java varargs"},
      {location: ["javaTools", "varargs"]},
{week: "4"},
  {name: "OOP"},
    {heading: "OOP: Polymorphism"},
      {subheading: "Polymorphism"},
        {location: ["oop", "polymorphism", "what"], omit_evidence: true},
        {location: ["oop", "inheritance", "overriding"], omit_evidence: true},
        {location: ["cppToJava", "inheritance", "polymorphism"], omit_evidence: true},
      {subheading: "Abstract Classes"},
        {location: ["oop", "inheritance", "abstractClasses"], omit_evidence: true},
        {location: ["uml", "classDiagrams", "abstractClasses", "what"], omit_evidence: true},
        {location: ["cppToJava", "inheritance", "abstractClassesAndMethods"], omit_evidence: true},
      {subheading: "Interfaces"},
        {location: ["oop", "inheritance", "interfaces"], omit_evidence: true},
        {location: ["uml", "classDiagrams", "interfaces", "what"], omit_evidence: true},
        {location: ["cppToJava", "inheritance", "interfaces"], omit_evidence: true},
  {name: "Requirements"},
    {heading: "Requirements analysis"},
      {location: ["requirements", "introduction"], omit_evidence: true},
      {location: ["requirements", "nonFunctionalRequirements"], omit_evidence: true},
      {location: ["requirements", "prioritizing"], omit_evidence: true},
      {location: ["requirements", "quality"], omit_evidence: true},
    {heading: "Techniques for gathering requirements"},
      {location: ["gatheringRequirements", "brainstorming"], omit_evidence: true},
      {location: ["gatheringRequirements", "productSurveys"], omit_evidence: true},
      {location: ["gatheringRequirements", "observation"], omit_evidence: true},
      {location: ["gatheringRequirements", "userSurveys"], omit_evidence: true},
      {location: ["gatheringRequirements", "interviews"], omit_evidence: true},
      {location: ["gatheringRequirements", "focusGroups"], omit_evidence: true},
    {heading: "Techniques for specifying requirements"},
      {subheading: "User Stories"},
        {location: ["specifyingRequirements", "userStories", "introduction"]},
        {location: ["specifyingRequirements", "userStories", "details"], omit_evidence: true},
        {location: ["specifyingRequirements", "userStories", "usage"]},
      {subheading: "Use Cases"},
        {location: ["specifyingRequirements", "useCases", "introduction"], omit_evidence: true},
        {location: ["specifyingRequirements", "useCases", "identifying"], omit_evidence: true},
        {location: ["specifyingRequirements", "useCases", "details"]},
        {location: ["specifyingRequirements", "useCases", "usage"], omit_evidence: true},
      {subheading: "Feature Lists"},
        {location: ["specifyingRequirements", "featureList", "what"], omit_evidence: true},
      {subheading: "Prose"},
        {location: ["specifyingRequirements", "prose", "what"], omit_evidence: true},
      {subheading: "Prototyping"},
        {location: ["gatheringRequirements", "prototyping"], omit_evidence: true},
      {subheading: "Glossary"},
        {location: ["specifyingRequirements", "glossary", "what"], omit_evidence: true},
      {subheading: "Supplementary Requirements"},
        {location: ["specifyingRequirements", "supplementaryRequirements", "what"], omit_evidence: true},
  {name: "Project Management"},
    {heading: "RCS: Workflows"},
      {subheading: "Branching"},
        {location: ["revisionControl", "branching"]},
        {location: ["gitAndGithub", "branch"]},
      {subheading: "Merge conflicts"},
        {location: ["gitAndGithub", "mergeConflicts"]},
      {subheading: "Pull requests"},
        {location: ["gitAndGithub", "createPRs"]},
        {location: ["gitAndGithub", "managePRs"]},
      {subheading: "Workflows"},
        {location: ["revisionControl", "drcsVsCrcs"], omit_evidence: true},
        {location: ["revisionControl", "forkingWorkflow"], omit_evidence: true},
        {location: ["gitAndGithub", "forkingWorkflow"]},
        {location: ["revisionControl", "featureBranchFlow"], omit_evidence: true},
        {location: ["revisionControl", "centralizedFlow"], omit_evidence: true},
{week: "5"},
  {name: "Implementation"},
    {heading: "Can use Generics in Java"},
      {location: ["cppToJava", "generics", "what"], omit_evidence: true},
      {location: ["cppToJava", "generics", "how"], omit_evidence: true},
    {heading: "Can use Java Collections"},
      {location: ["cppToJava", "collections", "what"]},
      {location: ["cppToJava", "collections", "arrayListClass"], omit_evidence: true},
      {location: ["cppToJava", "collections", "hashMapClass"], omit_evidence: true},
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
  {name: "Quality Assurance"},
      {heading: "Regression testing of text UIs"},
        {location: ["testing", "introduction", "what"]},
        {location: ["testing", "testingTypes", "regressionTesting", "what"]},
        {location: ["testing", "testAutomation", "what"], omit_evidence: true},
        {location: ["testing", "testAutomation", "testingTextUis"]},
      {heading: "Developer Testing: Basics"},
        {location: ["testing", "testingTypes", "developerTesting", "what"], omit_evidence: true},
        {location: ["testing", "testingTypes", "developerTesting", "why"]},
        {location: ["testing", "testAutomation", "usingTestDrivers"], omit_evidence: true},
        {location: ["testing", "testAutomation", "tools"], omit_evidence: true},
        {location: ["junit", "basic"]},
{week: "6"},
  {name: "Project Management"},
    {heading: "Continuous Integration/Deployment"},
      {location: ["integration", "introduction", "what"], omit_evidence: true},
      {location: ["integration", "buildAutomation", "what"]},
      {location: ["integration", "buildAutomation", "continuousIntegrationDeployment"]},
  {name: "Implementation"},
    {heading: "CodeQuality"},
      {subheading: "Readability"},
        {location: ["codeQuality", "maximiseReadability", "introduction"], omit_evidence: true},
        {location: ["codeQuality", "maximiseReadability", "basic", "avoidLongMethods"], omit_evidence: true},
        {location: ["codeQuality", "maximiseReadability", "basic", "avoidDeepNesting"], omit_evidence: true},
        {location: ["codeQuality", "maximiseReadability", "basic", "avoidComplicatedExpressions"], omit_evidence: true},
        {location: ["codeQuality", "maximiseReadability", "basic", "avoidMagicNumbers"], omit_evidence: true},
        {location: ["codeQuality", "maximiseReadability", "basic", "makeCodeObvious"], omit_evidence: true},
        {location: ["codeQuality", "maximiseReadability", "intermediate", "structureCodeLogically"], omit_evidence: true},
        {location: ["codeQuality", "maximiseReadability", "intermediate", "dontTripReader"], omit_evidence: true},
        {location: ["codeQuality", "maximiseReadability", "intermediate", "practiceKISSing"], omit_evidence: true},
        {location: ["codeQuality", "maximiseReadability", "intermediate", "avoidPrematureOptimizations"], omit_evidence: true},
        {location: ["codeQuality", "maximiseReadability", "intermediate", "slapHard"], omit_evidence: true},
        {location: ["codeQuality", "maximiseReadability", "advanced", "makeHappyPathProminent"], omit_evidence: true},
      {subheading: "Naming"},
        {location: ["codeQuality", "nameWell", "introduction"], omit_evidence: true},
        {location: ["codeQuality", "nameWell", "basic", "nounsAndVerbsAsNames"], omit_evidence: true},
        {location: ["codeQuality", "nameWell", "basic", "useStandardWords"], omit_evidence: true},
        {location: ["codeQuality", "nameWell", "intermediate", "useNameExplain"], omit_evidence: true},
        {location: ["codeQuality", "nameWell", "intermediate", "notTooLongNorShort"], omit_evidence: true},
        {location: ["codeQuality", "nameWell", "intermediate", "avoidMisleadingNames"], omit_evidence: true},
      {subheading: "Unsafe Practices"},
        {location: ["codeQuality", "avoidShortcuts", "introduction"], omit_evidence: true},
        {location: ["codeQuality", "avoidShortcuts", "basic", "useDefaultBranch"], omit_evidence: true},
        {location: ["codeQuality", "avoidShortcuts", "basic", "dontRecycleVarsOrParams"], omit_evidence: true},
        {location: ["codeQuality", "avoidShortcuts", "basic", "avoidEmptyCatchBlocks"], omit_evidence: true},
        {location: ["codeQuality", "avoidShortcuts", "basic", "deleteDeadCode"], omit_evidence: true},
        {location: ["codeQuality", "avoidShortcuts", "intermediate", "minimiseVariableScope"], omit_evidence: true},
        {location: ["codeQuality", "avoidShortcuts", "intermediate", "minimiseCodeDuplication"], omit_evidence: true},
      {subheading: "Code Comments"},
        {location: ["codeQuality", "commentMinimally", "introduction"], omit_evidence: true},
        {location: ["codeQuality", "commentMinimally", "basic", "dontRepeatObvious"], omit_evidence: true},
        {location: ["codeQuality", "commentMinimally", "basic", "writeToReader"], omit_evidence: true},
        {location: ["codeQuality", "commentMinimally", "intermediate", "explainWhatWhyNotHow"], omit_evidence: true},
  {name: "Design"},
    {heading: "Design: Models"},
      {location: ["modeling", "introduction", "what"], omit_evidence: true},
      {location: ["modeling", "introduction", "how"]},
    {heading: "UML: Class/Ojbect Diagrams - Basics"},
      {location: ["modeling", "modelingStructures", "ooStructures"], omit_evidence: true},
      {location: ["modeling", "modelingStructures", "classDiagramsBasic"]},
      {location: ["modeling", "modelingStructures", "objectDiagrams"]},
      {location: ["uml", "miscellaneous", "objectVsClassDiagrams"], omit_evidence: true},
    {heading: "UML: Class Diagrams - Intermediate"},
      {location: ["uml", "notes", "notes"], omit_evidence: true},
      {location: ["uml", "notes", "constraints"], omit_evidence: true},
      {location: ["uml", "classDiagrams", "associationsAsAttributes", "what"], omit_evidence: true},
      {location: ["modeling", "modelingStructures", "classDiagramsIntermediate"], omit_evidence: true},
{week: "7"},
  {name: "Design"},
    {heading: "UML: Sequence Diagrams - Basics"},
      {location: ["modeling", "modelingBehaviors", "sequenceDiagramsBasic"]},
    {heading: "UML: Sequence Diagrams - Intermediate"},
      {location: ["modeling", "modelingBehaviors", "sequenceDiagramsIntermediate"]},
      {location: ["uml", "sequenceDiagrams", "referenceFrames"], omit_evidence: true},
      {location: ["uml", "sequenceDiagrams", "parallelPaths"], omit_evidence: true},
    {heading: "Architecture"},
      {subheading: "Architecture Diagrams"},
        {location: ["design", "introduction", "what"], omit_evidence: true},
        {location: ["architecture", "architectureDiagrams", "reading"], omit_evidence: true},
        {location: ["designApproaches", "multilevelDesign", "what"]},
      {subheading: "Architectural Styles"},
        {location: ["architecture", "architecturalStyles", "introduction", "what"], omit_evidence: true},
        {location: ["architecture", "architecturalStyles", "nTier", "what"], omit_evidence: true},
        {location: ["architecture", "architecturalStyles", "clientServer", "what"], omit_evidence: true},
        {location: ["architecture", "architecturalStyles", "eventDriven", "what"]},
        {location: ["architecture", "architecturalStyles", "more", "moreStyles"], omit_evidence: true},
        {location: ["architecture", "architecturalStyles", "more", "usingStyles"]},
      {subheading: "APIs"},
        {location: ["reuse", "apis", "what"]},
    {name: "Implementation"},
      {heading: "Error Handling"},
        {subheading: "Logging"},
          {location: ["errorHandling", "logging", "what"], omit_evidence: true},
          {location: ["errorHandling", "logging", "how"]},
        {subheading: "Assertions"},
          {location: ["errorHandling", "assertions", "what"], omit_evidence: true},
          {location: ["errorHandling", "assertions", "how"]},
          {location: ["errorHandling", "assertions", "when"]},
        {subheading: "Exception Handling"},
          {location: ["errorHandling", "introduction", "what"], omit_evidence: true},
          {location: ["errorHandling", "exceptions", "what"], omit_evidence: true},
          {location: ["cppToJava", "exceptions", "what"], omit_evidence: true},
          {location: ["errorHandling", "exceptions", "how"]},
          {location: ["cppToJava", "exceptions", "how"], omit_evidence: true},
          {location: ["errorHandling", "exceptions", "when"], omit_evidence: true},
      {heading: "Advanced Java"},
        {subheading: "Streams"},
          {location: ["javaTools", "streamsBasic"]},
        {subheading: "Java: JavaFX"},
          {location: ["javaTools", "javaFXBasic"]},
{week: "8"},
  {name: "Requirements"},
    {heading: "Product design guidelines", priority: "3", file: "project.md#product_design", omit_evidence: true},
  {name: "Design"},
    {heading: "Design Principles: Basics"},
      {subheading: "Abstraction"},
        {location: ["designFundamentals", "abstraction", "what"], omit_evidence: true},
      {subheading: "Coupling"},
        {location: ["designFundamentals", "coupling", "what"]},
        {location: ["designFundamentals", "coupling", "how"]},
        {location: ["designFundamentals", "coupling", "types"]},
      {subheading: "Cohesion"},
        {location: ["designFundamentals", "cohesion", "what"]},
        {location: ["designFundamentals", "cohesion", "how"]},
      {subheading: "Some other principles"},
        {location: ["principles", "singleResponsibilityPrinciple"]},
        {location: ["principles", "openClosedPrinciple"]},
        {location: ["principles", "separationOfConcernsPrinciple"]},
  {name: "Implementation"},
    {heading: "Integration Approaches"},
      {location: ["integration", "approaches", "lateVsEarly"], omit_evidence: true},
      {location: ["integration", "approaches", "bigBangVsIncremental"], omit_evidence: true},
      {location: ["integration", "approaches", "topDownVsBottomUp"], omit_evidence: true},
  {name: "Quality Assurance"},
    {heading: "Types of Testing"},
      {subheading: "Unit Testing"},
        {location: ["testing", "testingTypes", "unitTesting", "what"]},
        {location: ["testing", "testingTypes", "unitTesting", "stubs"]},
        {location: ["testing", "dependencyInjection", "what"], omit_evidence: true},
        {location: ["testing", "dependencyInjection", "how"], omit_evidence: true},
      {subheading: "Integration Testing"},
        {location: ["testing", "testingTypes", "integrationTesting", "what"]},
        {location: ["testing", "testingTypes", "integrationTesting", "how"]},
      {subheading: "System Testing"},
        {location: ["testing", "testingTypes", "systemTesting", "what"]},
        {location: ["testing", "testAutomation", "testingGuis"]},
      {subheading: "Acceptance Testing"},
        {location: ["testing", "testingTypes", "acceptanceTesting", "what"]},
        {location: ["testing", "testingTypes", "acceptanceTesting", "acceptanceVsSystemTesting"]},
      {subheading: "Alpha/Beta Testing"},
        {location: ["testing", "testingTypes", "alphaBetaTesting", "what"]},
  {name: "Project Management"},
    {heading: "Project Mgt: Scheduling and Tracking"},
      {location: ["projectPlanning", "milestones"]},
      {location: ["projectPlanning", "buffers"]},
      {location: ["projectPlanning", "issueTrackers"]},
      {location: ["projectPlanning", "workBreakdownStructure"]},
      {location: ["projectPlanning", "ganttCharts"], omit_evidence: true},
      {location: ["projectPlanning", "pertCharts"], omit_evidence: true},
      {location: ["teamwork", "teamStructures"]},
  {name: "UML"},
    {heading: "Association Classes"},
      {location: ["oop", "associations", "associationClasses"]},
{week: "9"},
  {name: "Design"},
    {heading: "Basic Design Approaches"},
      {location: ["designApproaches", "topDownBottomUp", "what"], omit_evidence: true},
      {location: ["designApproaches", "agileDesign", "what"], omit_evidence: true},
    {heading: "Design Principles: Intermediate-Level"},
      {subheading: "How Polymorphism Works"},
        {location: ["oop", "inheritance", "substitutability"], omit_evidence: true},
        {location: ["oop", "inheritance", "dynamicAndStaticBinding"], omit_evidence: true},
        {location: ["oop", "polymorphism", "how"]},
      {subheading: "More Design Principles"},
        {location: ["principles", "liskovSubstitutionPrinciple"]},
        {location: ["principles", "lawOfDemeter"]},
        {location: ["principles", "interfaceSegregationPrinciple"], omit_evidence: true},
        {location: ["principles", "dependencyInversionPrinciple"], omit_evidence: true},
        {location: ["principles", "solidPrinciples"], omit_evidence: true},
        {location: ["principles", "yagniPrinciple"], omit_evidence: true},
        {location: ["principles", "dryPrinciple"], omit_evidence: true},
        {location: ["principles", "brooksLaw"], omit_evidence: true},
    {heading: "UML: Activity Diagrams"},
        {location: ["modeling", "modelingBehaviors", "activityDiagrams"]},
        {location: ["modeling", "modelingBehaviors", "activityDiagramsIntermediate"], omit_evidence: true},
  {name: "Quality Assurance"},
    {heading: "Testing: Intermediate Techniques"},
      {location: ["testing", "introduction", "testability"], omit_evidence: true},
      {location: ["testing", "testCoverage", "what"]},
      {location: ["testing", "testCoverage", "how"]},
      {location: ["junit", "intermediate"]},
      {location: ["testing", "tdd", "what"], omit_evidence: true},
    {heading: "Other QA Techniques"},
      {location: ["qualityAssurance", "introduction", "what"], omit_evidence: true},
      {location: ["qualityAssurance", "introduction", "validationVsVerification"]},
      {location: ["qualityAssurance", "codeReviews", "what"]},
      {location: ["qualityAssurance", "staticAnalysis", "what"]},
      {location: ["qualityAssurance", "formalVerification", "what"], omit_evidence: true},
  {name: "Documentation"},
    {heading: "Writing Developer Documents"},
      {subheading: "Type of Developer Docs"},
        {location: ["documentation", "introduction", "what"]},
      {subheading: "Guideline: Aim for Comprehensibility"},
        {location: ["documentation", "guidelines", "aimForComprehensibility", "what"], omit_evidence: true},
        {location: ["documentation", "guidelines", "aimForComprehensibility", "how"]},
      {subheading: "Guideline: Describe Top-Down"},
        {location: ["documentation", "guidelines", "goTopDown", "what"], omit_evidence: true},
        {location: ["documentation", "guidelines", "goTopDown", "why"]},
        {location: ["documentation", "guidelines", "goTopDown", "how"]},
      {subheading: "Guideline: Minimal but Sufficient"},
        {location: ["documentation", "guidelines", "documentMinimally", "what"], omit_evidence: true},
        {location: ["documentation", "guidelines", "documentMinimally", "how"], omit_evidence: true},
      {subheading: "Drawing Architecture Diagrams"},
        {location: ["architecture", "architectureDiagrams", "drawing"], omit_evidence: true},
{week: "10"},
  {name: "Design"},
    {heading: "Design Patterns: Basics"},
      {subheading: "Introduction"},
        {location: ["designPatterns", "introduction", "what"], omit_evidence: true},
        {location: ["designPatterns", "introduction", "format"], omit_evidence: true},
      {subheading: "Singleton pattern"},
        {location: ["designPatterns", "singleton", "what"]},
        {location: ["designPatterns", "singleton", "implementation"]},
        {location: ["designPatterns", "singleton", "evaluation"]},
      {subheading: "Facade pattern"},
        {location: ["designPatterns", "facade", "what"]},
      {subheading: "Command pattern"},
        {location: ["designPatterns", "command", "what"]},
      {subheading: "Abstraction Occurrence pattern"},
        {location: ["designPatterns", "abstractionOccurrence", "what"]},
  {name: "Quality Assurance"},
    {heading: "Test Case Design"},
      {location: ["testCaseDesign", "introduction", "what"]},
      {location: ["testing", "testingTypes", "exploratoryVsScriptedTesting", "what"]},
      {location: ["testing", "testingTypes", "exploratoryVsScriptedTesting", "when"], omit_evidence: true},
      {location: ["testCaseDesign", "introduction", "positiveVsNegative"]},
      {location: ["testCaseDesign", "introduction", "blackVsGlass"]},
      {location: ["testCaseDesign", "more", "testingUseCases"]},
    {heading: "Equivalence Partitioning"},
      {location: ["testCaseDesign", "equivalencePartitions", "what"], omit_evidence: true},
      {location: ["testCaseDesign", "equivalencePartitions", "basic"], omit_evidence: true},
      {location: ["testCaseDesign", "equivalencePartitions", "intermediate"]},
    {heading: "Boundary Value Analysis"},
      {location: ["testCaseDesign", "boundaryValueAnalysis", "what"], omit_evidence: true},
      {location: ["testCaseDesign", "boundaryValueAnalysis", "how"], omit_evidence: true},
{week: "11"},
  {name: "Design"},
    {heading: "Design Patterns: Intermediate-Level"},
      {location: ["designPatterns", "modelViewController", "what"]},
      {location: ["designPatterns", "observer", "what"]},
      {location: ["designPatterns", "more", "otherDesignPatterns"]},
      {location: ["designPatterns", "more", "combiningDesignPatterns"]},
      {location: ["designPatterns", "more", "usingDesignPatterns"]},
      {location: ["designPatterns", "more", "vsPrinciples"], omit_evidence: true},
      {location: ["designPatterns", "more", "otherTypesOfPatterns"]},
    {heading: "Other UML Models"},
      {location: ["modeling", "modelingStructures", "deploymentDiagrams"], omit_evidence: true},
      {location: ["modeling", "modelingStructures", "componentDiagrams"], omit_evidence: true},
      {location: ["modeling", "modelingStructures", "packageDiagrams"], omit_evidence: true},
      {location: ["modeling", "modelingStructures", "compositeStructureDiagrams"], omit_evidence: true},
      {location: ["modeling", "modelingBehaviors", "timingDiagrams"], omit_evidence: true},
      {location: ["modeling", "modelingBehaviors", "interactionOverviewDiagrams"], omit_evidence: true},
      {location: ["modeling", "modelingBehaviors", "communicationDiagrams"], omit_evidence: true},
      {location: ["modeling", "modelingBehaviors", "stateMachineDiagrams"], omit_evidence: true},
  {name: "Quality Assurance"},
    {heading: "Combining Multiple Test Inputs"},
      {location: ["testCaseDesign", "combiningTestInputs", "why"], omit_evidence: true},
      {location: ["testCaseDesign", "combiningTestInputs", "combinationStrategies"], omit_evidence: true},
      {location: ["testCaseDesign", "combiningTestInputs", "heuristicValid"], omit_evidence: true},
      {location: ["testCaseDesign", "combiningTestInputs", "heuristicInvalid"], omit_evidence: true},
      {location: ["testCaseDesign", "combiningTestInputs", "mix"]},
  {name: "Project Management"},
    {heading: "SDLC Process Models"},
      {location: ["processModels", "introduction", "what"], omit_evidence: true},
      {location: ["processModels", "introduction", "sequentialModels"]},
      {location: ["processModels", "introduction", "iterativeModels"]},
      {location: ["processModels", "introduction", "agileModels"]},
      {location: ["processModels", "exampleProcessModels", "scrum"], evidence: "project.md#relate_process"},
      {location: ["processModels", "exampleProcessModels", "xp"], evidence: "project.md#relate_process"},
      {location: ["processModels", "exampleProcessModels", "unifiedProcess"], evidence: "project.md#relate_process"},
      {location: ["processModels", "more", "cmmi"], omit_evidence: true},
      {location: ["processModels", "summary", "recap"], omit_evidence: true},
{week: "12"},
  {name: "Implementation"},
    {heading: "Reuse: Frameworks, Libraries, Platforms"},
      {subheading: "Reuse"},
        {location: ["reuse", "introduction", "what"], omit_evidence: true},
        {location: ["reuse", "introduction", "when"]},
      {subheading: "Libraries"},
        {location: ["reuse", "libraries", "what"]},
        {location: ["reuse", "libraries", "how"]},
      {subheading: "Frameworks"},
        {location: ["reuse", "frameworks", "what"]},
        {location: ["reuse", "frameworks", "frameworksVsLibraries"]},
      {subheading: "Platforms"},
        {location: ["reuse", "platforms", "what"]},
    {heading: "Cloud Computing"},
      {location: ["reuse", "cloudComputing", "what"], omit_evidence: true},
      {location: ["reuse", "cloudComputing", "services"], omit_evidence: true},
{week: "13"}
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


{% macro show_week_schedule(week_num_string, path="") %}

{% set week_num_int = week_num_string | int %}
{% set week = weeks[week_num_int - 1] %}

<include src="../../common/header.md" />

<div class="website-content" id="main">

{{ show_nav_buttons(week.num) }}

{{ show_week_schedule_body(week, path) }}

</div>

{% endmacro %}


{% macro show_nav_buttons(week_num) %}
{% set week_num = week_num | int %}
{% if week_num != 1 %}<span style="float:left"><md>[{{ glyphicon_chevron_left }} Previous Week]({{ baseUrl }}/schedule/week{{ (week_num - 1) }}/)</md></span>{% endif %}{% if week_num != 13 %}<span style="float:right"><md>[Next Week {{ glyphicon_chevron_right }}]({{ baseUrl }}/schedule/week{{ (week_num + 1) }}/)</md></span>{% endif %}<br>

{% endmacro %}


{% macro show_week_schedule_body(week, path="") %}

# Week {{ week.num }} <small><small>%%[{{ week.day }}]%%</small></small>

<tabs>
  <tab header="{{ icon_announcement }} Notices">
    <include src="{{ path }}notices-{{ module | lower }}.md" optional />
  </tab>
  <tab header="{{ icon_outcome }} Topics">
    <include src="{{ path }}topics.md" />
  </tab>
  <tab header="{{ icon_project }} Project">
    <include src="{{ path }}project.md" optional />
  </tab>
  <tab header="{{ icon_tutorial }} Tutorial">
    <include src="{{ path }}tutorial-{{ module | lower }}.md" optional />
  </tab>
  <tab header="{{ icon_info }} Admin Info">
    <include src="{{ path }}admin.md" />
  </tab>
</tabs>

{% endmacro %}




<!-- ============================= page content ============================================ -->

<include src="../common/header.md" />

<div class="website-content" id="main">

{{ show_nav_buttons(current_weeks[0]) }}

{% for week in weeks %}
{% set week_num = week.num | int %}
{% if week.num in current_weeks %}
  {{ show_week_schedule_body(week, "week" + week_num + "/") }}
<br>
<br>
{% endif %}
{% endfor %}

</div>