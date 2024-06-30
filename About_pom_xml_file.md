Notes about the Project Model Object XML file.(pom.xml file)
=============================================================================================

-> Purpose of the pom.xml file.
---------------------------------------------------------------------------------------------
	(1) It contains information about the project and configuration information (such as
	    dependencies and their versions, build plugins) for maven to buid the project.


-> Elements of the pom.xml file and their description.
---------------------------------------------------------------------------------------------
	(1) project:
	    The project element is the root element of the pom.xml file. The project element 
	    houses/ all the other elements of the pom.xml file.

	(2) modelVersion:
	    Is a sub element of the project element. It specifies the version of the project 
            descriptor. For Maven 2 and 3, its set to 4.0.0 (This value indicates compatibility
	    with Maven 3.)

	(3) groupId:
	     Is a sub element of the project element. It uniquely identifies the project or module
             within a large organiszation or ecosystem. The groupId coupled with the artifactId and
             version, form the fully qualified artifact name.
	
	(4) artifactId:
	     Is a sub element of the project element. It serves as the identifier(id) of the project 
	     within its group. Its the name by which the project is known.

	(5) version:
	    Is a sub element of the project element. It denotes the current version of the project.

	(6) packaging:
	    Is a sub element of the project element. It specifies the kind of packaging / type of artifact
	    the project produces when compiled/run. Examples include. jar(Java Archive) file for compiled java classes, 
	    war (Web Application Archive) for web applications. Others include ear, ejb, rar, app-client/acr, shade, 
	    source, jlink, source, jmod.

	(7) properties:
	    Is a sub element of the project element. It serves as a container for defining Maven properties. 
	    Properties are used to customize the behavoiur of Maven and its plugins. Maven properties are value plcaeholders.
	    Their values are accesible anywhere within a POM by using the notation ${property}

	(8) dependencies:
	    Is a sub element of the project element. This element houses the list of dependencies required
	    by the project. Each dependency (<dependency> defines a dependency) is defined by its groupId, 
	    artifactId, version and scope.

	(9) scope:
	    This element is used to define how a dependency is used during different phases of the build
	    process and runtime. It can take 6 values namely: 
			
			- compile (default scope) -> Compile dependencies are avaialble in project classpaths and
					           are propagated to dependent projects, 
			- provided -> Indicates that you expect the JSK or container to provide the dep[endency at runtime.
			- runtime -> Indicates that the dependency is not required for project compilitaion but is needed
                                     for execution. 
			- test -> Indicates that this depedency is used only for test compiltaion and execution but not required 
				  for normal app use.
			- system -> Indicates that this dependency is always available as a JAR file and no need to be 
				     to be looked up in a repository.
			- import -> Used on a pom dependency.

	(10) repositories:
		This elements defines the list of remote repositories from which dependencies and plugins can be downloaded.
		- plugin repository element specifies a remote location of where maven cane find new plugins
		
