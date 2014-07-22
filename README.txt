This is a temporary project to allow Apache Jetspeed portal to deploy to OSGI container. 
Currently, using Karaf 4 SNAPSHOT and Jetspeed 2.3.0-SNAPSHOT.


In the following two cases, you need to properly configue the DataSource in
src/main/webapp/META-INF/context.xml

And add your DB driver to tomcat server if you are deploying as a war. Or add
it directly as a dependency for OSGI (more on this later).

Deploy to Tomcat 7:
===================

Run the following command:

$ mvn clean pacakge -P shared-libs

This will generate a war file "target/jetspeed.war" and a directory
"target/tomcat-shared-libs".

Copy the WAR file to TOMCAT/webapps, and the shared libs folder

Try to access http://localhost:8080/jetspeed


Deploy to Karaf-4 SNAPSHOT: (This is still not working)
======================================================

On a newly unpacked karaf :

feature:install pax-war-tomcat

To build this project :

$ mvn -P osgi clean package 

copy the resulting war file to KARAF_HOME/deploy

Try to access http://localhost:8181/jetspeed


TODO, improve the build to allow different JS2 config (jet-ui, or classic).



