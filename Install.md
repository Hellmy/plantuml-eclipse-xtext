An Xtext Language Built with Maven
==================================

This project structure is based on the xtext example my.mavenized.herolanguage
 

Steps:
======

### 1. Increase memory.

```
   export MAVEN_OPTS="-Xmx512m -XX:MaxPermSize=256m"
   In eclipse:
   Add to the run configuration -> JRE -> Environment:
   -Xmx512m -XX:MaxPermSize=256m
```

### 2. Build the language

###### 2.1. Build with maven

```
 cd plantuml.eclipse.releng/
 mvn clean install
```

###### 2.2. Build with eclipse

```
* Import all project files
* Right click on "GeneratePumlLanguage.mwe2" (Project: plantuml.eclipse)-> Run As -> Run MWE2 Workflow
* Right click on the project "plantuml.eclipse" -> Run As -> Eclipse Application
```

### 3. Install via updatesite

```
* "Help->Install New Software..." 
* Enter URL/Path to the updatesite (<plantuml-eclipse>/plantuml.eclipse.updatesite/target/repository/)
* Select all packages and proceed.
* Restart eclipse after successful installation
* Create an empty project
* Create file "<filename>.puml"
  - be aware about the suffix ".puml", this will connect the editor to the plantuml-eclipse supported view
* Start UML description:
  - Start description of a sequence diagram:
    "SEQUENCE
     @startuml
     <plantuml code>
     @enduml
    "
  - Start description of component diagram:
    "COMPONENT
     @startuml
     <plantuml code>
     @enduml
    "
* Use "ctrl-space" for possible commands in the <plantuml code> section
  - supports the uppercase typing!
  - sequence and component commands should be available - appropiate to the choosen start description
```
  
  