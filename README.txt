= Ubimix projects =

This project contains Maven configuration files used to checkout all projects
from remote repositories, build and install them. This configuration 
is used also to prepare Eclipse development environment.

== How to checkout all projects? ==
 
> mvn initialize -P checkout

All projects to checkout with their repository URLs are loaded from the file 
defined by the "projectListFile" variable. By default it is the 
"./projects.json" file. To re-define the list of projects to checkout:
> mvn initialize -P checkout -DprojectListFile=myfile.json

By default this task checks out all projects in the "./projects" subfolder in 
this project. How to re-define this parameter - see below. 

== How to compile and install all projects? ==

> mvn clean install

By default this task seek all projects to build in the "./projects" subfolder in 
this project. How to re-define this parameter - see below. 

== How to prepare Eclipse development environment? ==

> mvn eclipse:clean eclipse:eclipse

This command builds all required Eclipse configuration files. 

== How to import projects into Eclipse ? ==

To import projects in the Eclipse workspace you need to perform the following
actions:
* "File" > "Import..."
* Select "General" > "Existing Projects into Workspace"
* Click the "Next >" button
* In the field "Select root directory:" put the full path to the "./projects"
  sub-folder. You can use a dialog box activated by the "Browse..." button and 
  click "Validate". 
* Select all projects and click the "Finish" button. 
  Note: You should uncheck the "Copy projects into workspace" option to avoid 
  duplication of projects on your disk. 

== How to re-define the project checkout and build directory? ==

All projects are checked out and compiled in the folder defined by 
the "workspaceDir" variable. This variable contains a path relative to the
"checkout" or "build" directory. So the "../projects" value points to the
"projects" sub-folder in this project.  

To re-define the project folder:
> mvn initialize -P checkout -DworkspaceDir=../ubimix-projects
> mvn clean install -DworkspaceDir=../ubimix-projects

In this case all projects are checked out and compiled in the "ubimix-projects"
sub-folder.
