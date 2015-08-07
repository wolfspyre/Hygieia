Jenkins Cucumber Test Collector
=================

This project uses Spring Boot to package the collector as an executable JAR with dependencies.

Building and Deploying
--------------------------------------

Run mvn install to package the collector into an executable JAR file. Copy this file to your server and launch it using
java -JAR subversion-collector.jar. You will need to provide an application.properties file that contains information about how
to connect to the Dashboard MongoDB database instance, as well as properties the Subversion collector requires. See
the Spring Boot [documentation](http://docs.spring.io/spring-boot/docs/current-SNAPSHOT/reference/htmlsingle/#boot-features-external-config-application-property-files)
for information about sourcing this properties file.

###Sample application.properties file
--------------------------------------

    #Database Name - default is test
    spring.data.mongodb.database=dashboard

    #Database HostName - default is localhost
    spring.data.mongodb.host=10.0.1.1

    #Database Port - default is 27017
    spring.data.mongodb.port=9999

    #Database Username - default is blank
    spring.data.mongodb.username=db

    #Database Password - default is blank
    spring.data.mongodb.password=dbpass

    #Collector schedule (required)
    subversion.cron=0 0/5 * * * *

    #Shared subversion username and password
    subversion.username=foo
    subversion.password=bar

    #Maximum number of days to go back in time when fetching commits
    subversion.commitThresholdDays=15



