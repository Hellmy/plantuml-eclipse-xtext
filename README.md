For installation instructions, see install.md



Basic Tool:
PlantUml (http://plantuml.sourceforge.net/) is an UML-Tool which enables a description of UML diagrams via text.
PlantUml itself is distributed under the GPL license and is also available as eclipse plugin (http://plantuml.sourceforge.net/eclipse.html)


Problem:
The eclipse plugin itself provides no further support during the modelling or syntax highlighting.


Solution:
This is an early alpha plugin plantuml-eclipse providing a basic highlighting, outline support and content assistance.


plantuml-eclipse features:
* Sequence Diagram:
  - Basic syntax highlighting
  - Content assistance (plantuml keywords, connection between named elements)
  - Outline support (eclipse view "outline" or shortcut "ctrl-o")
* Component Diagram:
  - Basic syntax highlighting
  - Content assistance (plantuml keywords, connection between named elements)


plantuml-eclipse limitations:
* Some possible plantuml commands are missing --> Errors in Eclipse but no limitation during usage
* Currently more support for sequence diagrams (Feedback welcome!)
* Partial support for component diagrams (Feedback welcome!)
* Plantuml keywords must be typed in UPPERCASES! (e. g. PARTICIPANT....)
  - Necessary to differ between normal descriptions and keywords
  - Alternative could be an own lexer (Could be a possibility I found after some research but I have no idea how to - Some experience welcome!)


Technical plantuml-eclipse background information:
* xtext as source
* maven to build
* jenkins to deploy update site - perhaps the url will change!
* Reporting bugs:
  - Latest Version?
  - Example plantuml code (small!) or steps to reproduce the bug
  - Observed (buggy) behaviour
  - Expected behaviour
 

plantuml-eclipse usage:
* Installation instructions described in the install.md (you should run the maven build for instance)
* It is also possible to install the plugin in eclipse after a successful build  
  - "Help->Install New Software..." 
  - Enter URL/Path to the updatesite (<plantuml-eclipse>/plantuml.eclipse.updatesite/target/repository/)
  - Select all packages and proceed.
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


Basic examples:
SEQUENCE
@startuml
PARTICIPANT test
PARTICIPANT test2
test -> test2
PARTICIPANT "fo\n123l l" AS lol
PARTICIPANT "fooLong" AS foo
foo --> lol
foo <-- lol
foo <- lol
[<- lol
@enduml
