= Ubimix projects =

This project contains Maven configuration files used to checkout all projects
from remote repositories, build and install them. This configuration 
is used also to prepare the Eclipse development environment.

== How to checkout all projects? ==
 
> mvn initialize -P checkout

All projects to checkout with their repository URLs are loaded from the file 
defined by the "projectListFile" variable. By default it is the 
"./projects.json" file. To re-define the list of projects to checkout:
> mvn initialize -P checkout -DprojectListFile=myfile.json

== How to compile and install all projects? ==

> mvn clean install

== How to prepare Eclipse development environment? ==

> mvn eclipse:clean eclipse:eclipse

== How to re-define the project checkout and build directory? ==

All projects are checked out and compiled in the folder defined by 
the "workspaceDir" variable. By default "workspaceDir" is "../projects" 
(relative to this folder) so all remote projects are stored at the 
same level as this project in the "projects" sub-folder.

To re-define the project folder:
> mvn initialize -P checkout -DworkspaceDir=../ubimix-projects
> mvn clean install -DworkspaceDir=../ubimix-projects
