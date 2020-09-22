IDEA Maven Plugin
=================
[![Build Status](https://buildhive.cloudbees.com/job/zhve/job/idea-maven-plugin/badge/icon)](https://buildhive.cloudbees.com/job/zhve/job/idea-maven-plugin/)

**idea-maven-plugin** creates IDEA workspace files **.iml**, **.ipr** and **.iws** with your own settings based only on project structure and given profile.

Intro
-----
Maven Integration (build-in plugin to open maven projects in IDEA) is a good choice when you just want to create a project from scratch.
If you want some specific project settings to take place, then you have to set it up manually.
Unfortunately, Maven Integration doesn't have any configuration file, it just opens your project with default settings. If you want your own, this plugin for you.

How to Use
----------
IDEA Maven Plugin is not deployed to Maven Central yet, so you have to:

- mvn install this plugin in your local repo as jar

- run the following in a directory with pom.xml (root pom)


`mvn com.github.zhve:idea-maven-plugin:3.0b1-patched:idea`

If you want to use non default settings, save [idea.bat](https://raw.githubusercontent.com/zhve/idea-maven-plugin/master/src/main/resources/ideaplugin/idea.bat) to your project root, edit parameters, and run:

Create workspace: `idea idea`

Delete workspace: `idea clean`

Parameters
----------
**COMMON**
<table>
<tr>
  <th>Parameter name</th>
  <th>Description</th>
  <th>Default value</th>
</tr>
<tr>
  <td>jdkName</td>
  <td>Name of the registered IDEA SDK</td>
  <td>1.7</td>
</tr>
<tr>
  <td>jdkLevel</td>
  <td>Name of the project language level</td>
  <td>JDK_1_7</td>
</tr>
<tr>
  <td>wildcardResourcePatterns</td>
  <td>Resource pattern in wildcard format, for example ?*.xml;?*.properties</td>
  <td>!?*.java</td>
</tr>
<tr>
  <td>compileInBackground</td>
  <td>Enable/disable compilation in background</td>
  <td>true</td>
</tr>
<tr>
  <td>assertNotNull</td>
  <td>Enable/disable adding assertion for @NotNull at run-time</td>
  <td>false</td>
</tr>
</table>

**PROJECT**
<table>
<tr>
  <th>Parameter name</th>
  <th>Description</th>
  <th>Default value</th>
</tr>
<tr>
  <td>autoscrollToSource</td>
  <td>Autoscroll to Source (Project Pane)</td>
  <td>false</td>
</tr>
<tr>
  <td>autoscrollFromSource</td>
  <td>Autoscroll from Source (Project Pane)</td>
  <td>false</td>
</tr>
<tr>
  <td>buildProcessHeapSize</td>
  <td>Build Process Heap Size (Project Pane)</td>
  <td>1536</td>
</tr>
<tr>
  <td>mavenThreads</td>
  <td>Maven Threads Param (Maven Settings pane)</td>
  <td>4</td>
</tr>
<tr>
  <td>hideEmptyPackages</td>
  <td>Compact Empty Middle Packages (Project Pane)</td>
  <td>true</td>
</tr>
<tr>
  <td>sortByType</td>
  <td>Sort by Type (Project Pane)</td>
  <td>false</td>
</tr>
<tr>
  <td>optimizeImportsBeforeCommit</td>
  <td>Optimize imports before commit</td>
  <td>true</td>
</tr>
<tr>
  <td>reformatCodeBeforeCommit</td>
  <td>Reformat code before commit</td>
  <td>false</td>
</tr>
<tr>
  <td>performCodeAnalysisBeforeCommit</td>
  <td>Perform code analysis before commit</td>
  <td>false</td>
</tr>
</table>

**JEE**
<table>
<tr>
  <th>Parameter name</th>
  <th>Description</th>
  <th>Default value</th>
</tr>
<tr>
  <td>applicationServerTitle</td>
  <td>Run/Debug Configuration menu item</td>
  <td>[empty]</td>
</tr>
<tr>
  <td>applicationServerName</td>
  <td>Application server: Tomcat or Jetty</td>
  <td>Tomcat</td>
</tr>
<tr>
  <td>applicationServerVersion</td>
  <td>Full version of the application server</td>
  <td>7.0.54</td>
</tr>
<tr>
  <td>applicationServerFullName</td>
  <td>Full name of the application server</td>
  <td>[empty]</td>
</tr>
<tr>
  <td>selectedWarArtifactId</td>
  <td>Selected configuration in Run/Debug menu</td>
  <td>[empty]</td>
</tr>
<tr>
  <td>vmParameters</td>
  <td>VM parameters for the application server</td>
  <td>[empty]</td>
</tr>
<tr>
  <td>openInBrowser</td>
  <td>On/Off browser auto launch</td>
  <td>false</td>
</tr>
<tr>
  <td>openInBrowserUrl</td>
  <td>Start the browser at this url</td>
  <td>http://localhost:8080</td>
</tr>
<tr>
  <td>deploymentContextPath</td>
  <td>deployment application context path</td>
  <td>/</td>
</tr>
<tr>
  <td>assembleModulesIntoJars</td>
  <td>On/Off assembling modules to jars</td>
  <td>true</td>
</tr>
<tr>
</table>

**GAE**
<table>
<tr>
  <th>Parameter name</th>
  <th>Description</th>
  <th>Default value</th>
</tr>
<tr>
  <td>gaeHome</td>
  <td>Google App Engine Java SDK home directory</td>
  <td>[empty]</td>
</tr>
</table>