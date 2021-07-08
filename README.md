# ApacheMavenProj001
# Apache Maven web app

# Prerequisites:

To complete this quickstart:

* Installing Maven

To install Maven on your own system (computer), go to the Maven download page and follow the instructions there. In summary, what you need to do is:

Set the JAVA_HOME environment variable to point to a valid Java SDK (e.g. Java 8).

Download and unzip Maven.

Set the M2_HOME environment variable to point to the directory you unzipped Maven to.

Set the M2 environment variable to point to M2_HOME/bin (%M2_HOME%\bin on Windows, $M2_HOME/bin on unix).

Add M2 to the PATH environment variable (%M2% on Windows, $M2 on unix).

Open a command prompt and type 'mvn -version' (without quotes) and press enter.

* Creating the Project Directory

Once you have assured that Maven is installed, create a new directory somewhere on your hard disk. This directory will be the root directory for your first Maven project.

* Creating the POM File

Once you have created the project root directory, create a file called pom.xml inside the directory.


Inside the pom.xml file you put the following XML:


<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
                      http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>


    <groupId>com.SDK</groupId>

    <artifactId>hello-world</artifactId>

    <version>1.0.0</version>

</project>

This is a minimal pom.xml file.

The groupId identifies your organization.

The artifactId identifies the project. More specifically, it identifies the artifact built from the project, like for instance a JAR file.

The version identifies the version of the artifact which the POM file builds. When you evolve the project and you are ready to release, remember to update the version number.

Other projects that need to use your artifact will refer to it using the groupId, artifactId and version, so make sure to set these to some sensible values.

* Testing the POM File

When you have created the pom.xml file inside the project root directory it is a good idea to just test that Maven works, and that Maven understands the pom.xml file.

To test the pom.xml file, open a command prompt and change directory (cd) into the project root directory. Then execute this command:

mvn clean

The mvn clean command will clean the project directory for any previous temporary build files. Since the project is all new, there will be no previous build files to delete. The command will succeed.

You will see that Maven writes what project it has found. It will output that to the command prompt. This is a sign that Maven understands your POM. Here is an example of what Maven could output:

C:\Utils\DevOps\Language-Runtime\apache-maven\ApacheMavenProj001>mvn clean
[INFO] Scanning for projects...
[INFO]
[INFO] ------------------------< com.SDK:hello-world >-------------------------
[INFO] Building hello-world 1.0.0
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- maven-clean-plugin:2.5:clean (default-clean) @ hello-world ---
[INFO] Deleting C:\Utils\DevOps\Language-Runtime\apache-maven\ApacheMavenProj001\target
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.279 s
[INFO] Finished at: 2021-07-08T13:29:12+01:00
[INFO] ------------------------------------------------------------------------

* Creating a Java Source Directory
Once you have tested the POM file works, create a Java source directory. The Java source directory should be located inside the standard directory layout. Basically, that means that should should create the following directory structure:

src
  main
    java

That means, a src directory inside the project root directory. Inside the src directory you create a main directory. Inside the main directory you create a java directory. The java directory is the root directory for your Java source code.

* Creating a Java Source File
Inside the Java root source directory (src/main/java) create a new directory (java package) called helloworld.

Inside the helloworld directory (java package) insert a file named HelloWorld.java. Inside the HelloWorld.java file you put the following Java code:

package helloworld;

public class HelloWorld {

	public static void main(String args[]){

		System.out.println("Hello World, Maven");

	}

}

Save the file.

* Building the Project

When you have created the Java source file, open a command prompt and change directory into the project root directory. Then execute this command:

mvn package

The mvn package command instructs Maven to run the package build phase which is part of the default build life cycle.

Maven should now run. Maven will compile the Java source file and create a JAR file containing the compiled Java class.

Maven creates a target subdirectory inside the project root directory. Inside the target directory you will find the finished JAR file, as well as lots of temporary files (e.g. a classes directory containing all the compiled classes).

The finished JAR file will be named after this pattern:

artifactId-version
So, based on the POM shown earlier in this tutorial, the JAR file will be named:

hello-world-1.0.0.jar



* Notes:





