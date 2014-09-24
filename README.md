Jenkins-Android
===============

Tutorial how to configure Jenkins with Android Projects Using both Eclipse and Android Studio


Summary

The following repository is a technical reference for a continuous integration of Android projects using Jenkins.

We will go step by step with detailed description to integrate a sample project to Jenkins.
1- install and configure of Jenkins
2- A sample project using both ant and gradle build system
3- Steps to configure a various build variants for our sample project (dev/prod variants)
   * Configure Ant build files using Eclipse ==> (dev/prod variants)
   * Configure Ant build files using Android System ==> (dev/prod variants)


1- install of Jenkins

Download jenkins.war file from jenkins website : http://jenkins-ci.org/
You can use Tomcat server to launch Jenkins by saving jenkins.war under Tomcat webapps folder 
(Path exp :C:\Program Files\Apache Software Foundation\Tomcat 6.0\webapps )
Launch tomcat and access Jenkins from : http://localhost:8080/jenkins/

2- install Android plugins for Jenkins

To install a new plugin with Jenkins, go under Administrer Jenkins, then select Gestion des plugins.
All you have to do now is to search for plugin and install it.

The following jenkins plugins are necessary to use Android Projects with Jenkins
*Android Emulator Plugin : allow us to launch Android emulator, install app and launch tests
*Ant Plugin : Necessary to compile projects using Ant
*Gradle Plugin : Necessary to compile projects using Gradle
*Subversion Plugin :allow us to get project code source using Tortoise SVN

3- Configure Jenkins for Android Project

To Add a new project to Jenkins, we have to create a New Item.
  *Steps to follow are :

  1-Name your Project
  2-Handle Source Code : Set up your repository URL using SVN or GIT 
  3-Build : Choose your android build system Ant/Gradle
  For project using Ant build system : Select option Add Build Step ==> Call Ant
                                       Then specify your ant target (defined in your build file)==>More details further
                                       Finally specify path to your build file. (Ex: Project Parent folder/build.xml)
  
  For project using Gradle build system : Select option Add Build Step ==> Invoke Gradle Script
                                          Select option Gradle Wrapper
                                          Finally specify the task to execute (Ex: clean build) 
                                          Gradle build file Path : app/build.gradle.==>More details further
