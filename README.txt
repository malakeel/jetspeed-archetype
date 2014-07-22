This is a temporary project to allow Apache Jetspeed portal to deploy to OSGI
container. Currently, using Karaf 4 SNAPSHOT and Jetspeed 2.2.2 (Will upgrade
to 2.3.0-SNAPSHOT)

On a newly unpacked karaf :

feature:install pax-war-tomcat

install mvn:javax.portlet/portlet-api/2.0

To build this project :

$ mvn -P osgi clean package 

copy the resulting war file to KARAF_HOME/deploy

try to access http://localhost:8181/jetspeed




